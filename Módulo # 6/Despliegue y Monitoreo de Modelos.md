<h1>Módulo 6: Despliegue y Monitoreo de Modelos</h1>

<h2>Objetivo</h2>
<p>En este módulo aprenderás cómo poner un modelo en producción, integrarlo como una API para que otras aplicaciones lo consuman, y monitorear su desempeño para detectar problemas como la deriva de datos (data drift) o la degradación de rendimiento.</p>

<hr>

<h2>¿Por qué es clave el despliegue?</h2>
<p>Entrenar un modelo es solo una parte del camino. El verdadero valor ocurre cuando ese modelo se convierte en un servicio usable por otras aplicaciones o usuarios. Por ejemplo:</p>
<ul>
    <li>📦 Un modelo de recomendación integrado en un e-commerce.</li>
    <li>📲 Un modelo de clasificación ejecutándose en una app móvil.</li>
    <li>📊 Un modelo predictivo alimentando dashboards en tiempo real.</li>
</ul>

<hr>

<h2>Opciones de despliegue en AWS</h2>
<p>AWS ofrece varias formas de exponer modelos como endpoints de inferencia. Cada una tiene ventajas y casos ideales:</p>

<table border="1">
<tr>
    <th>Opción</th>
    <th>Descripción</th>
    <th>Casos ideales</th>
</tr>
<tr>
    <td>SageMaker Endpoint</td>
    <td>Servicio gestionado que crea una API REST directamente desde un modelo entrenado en SageMaker.</td>
    <td>Modelos de cualquier tamaño, integración directa con SageMaker.</td>
</tr>
<tr>
    <td>AWS Lambda</td>
    <td>Función serverless que carga un modelo y responde a solicitudes. Ideal para modelos pequeños.</td>
    <td>Modelos ligeros (<50MB), predicciones rápidas y poco frecuentes.</td>
</tr>
<tr>
    <td>Amazon Fargate</td>
    <td>Modelo empaquetado como contenedor (Docker) y ejecutado en un clúster ECS sin servidores.</td>
    <td>Modelos más pesados, o cuando necesitas control total sobre el entorno de ejecución.</td>
</tr>
</table>

<hr>

<h2>Despliegue con SageMaker Endpoint (Ejemplo práctico)</h2>
<p>Si entrenaste un modelo en SageMaker, desplegarlo es directo:</p>

<pre><code>
from sagemaker.predictor import Predictor

predictor = xgb.deploy(
    instance_type='ml.m5.large',
    endpoint_name='mi-modelo'
)
</code></pre>

<p>Una vez desplegado, puedes hacer predicciones así:</p>

<pre><code>
import json

payload = {'inputs': [[3.5, 1.2, 5.3, 1.8]]}  # Ejemplo de iris
response = predictor.predict(json.dumps(payload))
print(response)
</code></pre>

<hr>

<h2>¿Cómo se conecta el endpoint a otras apps?</h2>
<p>Un SageMaker Endpoint es una API REST. Eso significa que puedes consumirla desde:</p>
<ul>
    <li>📲 Aplicaciones móviles.</li>
    <li>🌐 Aplicaciones web (backend).</li>
    <li>📊 Dashboards y procesos batch.</li>
</ul>

<p>Ejemplo con cURL:</p>
<pre><code>
curl -X POST \
     -H "Content-Type: application/json" \
     -d '{"inputs": [[3.5, 1.2, 5.3, 1.8]]}' \
     https://mi-endpoint.amazonaws.com/invocations
</code></pre>

<hr>

<h2>¿Qué es Model Monitor?</h2>
<p><strong>SageMaker Model Monitor</strong> es un servicio que revisa automáticamente el tráfico que recibe el endpoint y lo compara contra el perfil de los datos originales (los datos con los que entrenaste el modelo).</p>

<h3>Problemas que detecta:</h3>
<ul>
    <li>🚨 Cambios en la distribución de las variables (data drift).</li>
    <li>🚨 Nuevos valores inesperados (categorías que no existían antes).</li>
    <li>🚨 Problemas de calidad (datos faltantes o fuera de rango).</li>
</ul>

<h3>Configurar Model Monitor (flujo típico)</h3>
<ol>
    <li>✅ Capturar tráfico de predicciones (con Data Capture).</li>
    <li>✅ Crear un baseline de los datos originales (Training Data Baseline).</li>
    <li>✅ Crear una programación (schedule) para ejecutar el monitor periódicamente.</li>
    <li>✅ Revisar alertas en CloudWatch.</li>
</ol>

<pre><code>
from sagemaker.model_monitor import DataCaptureConfig

predictor = xgb.deploy(
    instance_type='ml.m5.large',
    endpoint_name='mi-modelo',
    data_capture_config=DataCaptureConfig(
        enable_capture=True,
        destination_s3_uri='s3://mi-bucket/captura/',
        capture_options=['Request', 'Response']
    )
)
</code></pre>

<p>Más adelante, el Data Capture se conecta con un Job de monitoreo:</p>
<pre><code>
from sagemaker.model_monitor import DefaultModelMonitor

monitor = DefaultModelMonitor(
    role=role,
    instance_count=1,
    instance_type='ml.m5.large',
    volume_size_in_gb=20,
    max_runtime_in_seconds=3600
)

monitor.schedule(
    endpoint_input=predictor.endpoint_name,
    output_s3_uri='s3://mi-bucket/monitoreo/',
    schedule_cron_expression='cron(0 12 * * ? *)'
)
</code></pre>

<hr>

<h2>Integración con CloudWatch</h2>
<p>Todos los logs, métricas y alertas de SageMaker Model Monitor se envían automáticamente a <strong>Amazon CloudWatch</strong>. 
Desde ahí puedes:</p>
<ul>
    <li>📊 Crear dashboards de monitoreo.</li>
    <li>🔔 Configurar alarmas si hay problemas de drift.</li>
    <li>📥 Integrar con notificaciones (SNS, email, Slack).</li>
</ul>

<hr>

<h2>Práctica recomendada: Despliegue + Monitoreo completo</h2>
<ol>
    <li>✅ Entrenar un modelo (puede ser con XGBoost como ejemplo).</li>
    <li>✅ Guardar el modelo en S3.</li>
    <li>✅ Crear endpoint en SageMaker.</li>
    <li>✅ Hacer algunas predicciones de prueba (Postman o Python).</li>
    <li>✅ Activar Data Capture y Model Monitor.</li>
    <li>✅ Revisar logs y métricas en CloudWatch.</li>
</ol>

<hr>

<h2>Enlaces útiles</h2>
<ul>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/deploy-model.html" target="_blank">Desplegar modelos en SageMaker</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html" target="_blank">Documentación Model Monitor</a></li>
    <li><a href="https://docs.aws.amazon.com/cloudwatch/" target="_blank">Introducción a CloudWatch</a></li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>Con esto, lograste desplegar un modelo como API real en AWS. 
Tu modelo ahora es parte de un sistema completo, capaz de ser usado por aplicaciones, reportes o cualquier otro consumidor. 
Y lo más importante: no es un sistema “ciego”, porque Model Monitor te ayudará a detectar si algo empieza a salir mal.</p>

<p>En el próximo módulo, aprenderemos cómo asegurar que este modelo esté protegido y cómo optimizar costos para que sea viable en producción.</p>
