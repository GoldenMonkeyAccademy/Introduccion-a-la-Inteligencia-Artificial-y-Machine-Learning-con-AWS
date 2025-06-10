<h1>Módulo 7: Seguridad y Optimización de Costos en AWS ML</h1>

<h2>Objetivo</h2>
<p>En este módulo aprenderás cómo proteger tus datos, modelos y pipelines de Machine Learning dentro de AWS. Además, aprenderás prácticas clave para 
optimizar los costos durante el entrenamiento, almacenamiento y despliegue de modelos. Un proyecto de ML exitoso no solo es preciso, sino seguro y costo-eficiente.</p>

<hr>

<h2>Seguridad: Protegiendo datos y modelos</h2>
<p>En un entorno cloud, los datos de entrenamiento y los modelos son activos valiosos que deben protegerse adecuadamente. En AWS, existen varias capas de seguridad:</p>

<h3>✅ Roles y Permisos (IAM)</h3>
<p>En AWS, cada servicio (S3, SageMaker, Glue) necesita permisos específicos. En vez de usar credenciales fijas, AWS recomienda asignar <strong>roles IAM</strong> 
con permisos mínimos (Principio de Menor Privilegio).</p>
<ul>
    <li>💡 SageMaker tiene su propio rol, que necesita acceso a S3 (datos y modelos), ECR (contenedores) y CloudWatch (logs).</li>
    <li>💡 Glue necesita permisos para leer de S3 y escribir en el Data Catalog.</li>
    <li>💡 Data Scientists pueden tener roles con permisos limitados (solo lectura, o solo en ciertos buckets).</li>
</ul>

<h3>✅ Cifrado de datos</h3>
<p>El cifrado es clave para proteger datos en reposo (en S3) y en tránsito (entre servicios). AWS ofrece:</p>
<ul>
    <li>🔐 <strong>S3 Encryption:</strong> Automáticamente cifra cada archivo cargado en S3.</li>
    <li>🔐 <strong>KMS (Key Management Service):</strong> Permite crear claves de cifrado gestionadas por el cliente (Customer Managed Keys).</li>
    <li>🔐 SageMaker Endpoints también pueden cifrar las predicciones almacenadas o capturadas para monitoreo.</li>
</ul>

<h3>✅ Control de acceso con Lake Formation</h3>
<p>Si manejas un Data Lake, <strong>AWS Lake Formation</strong> permite centralizar los permisos a nivel tabla o columna. Esto es ideal para asegurar 
que solo usuarios autorizados puedan ver ciertos datos (por ejemplo, ocultar datos sensibles como nombres o tarjetas).</p>

<hr>

<h2>Optimización de Costos: Buenas prácticas financieras</h2>
<p>Trabajar con Machine Learning en la nube puede volverse costoso si no controlas bien el uso de recursos. Estas son las estrategias recomendadas para ahorrar dinero sin comprometer la calidad:</p>

<h3>✅ Spot Instances para Entrenamiento</h3>
<p>Las <strong>Spot Instances</strong> son instancias EC2 sobrantes que AWS vende con descuentos de hasta el 70-90%. Si tu entrenamiento puede interrumpirse y reiniciarse (típico en batch), son una excelente opción.</p>

<p><strong>Ejemplo:</strong></p>
<pre><code>
estimator = XGBoost(
    instance_type='ml.m5.large',
    use_spot_instances=True,
    max_wait=3600
)
</code></pre>

<h3>✅ Pausar Endpoints fuera de horario</h3>
<p>Un error común es dejar modelos desplegados todo el tiempo, incluso cuando no se usan. En proyectos internos o demos, puedes:</p>
<ul>
    <li>⏸️ Detener endpoints automáticamente fuera de horario laboral.</li>
    <li>⚙️ Usar SageMaker Serverless Inference (paga solo por invocación).</li>
</ul>

<h3>✅ Elegir correctamente el tipo de instancia</h3>
<p>Más grande no siempre es mejor. Es clave entender las necesidades reales del modelo:</p>
<ul>
    <li>📊 Modelos pequeños (menos de 500MB): ml.m5.large o ml.c5.large.</li>
    <li>📈 Modelos grandes (GBs o múltiples deep learning layers): ml.p3 o ml.g5 (con GPU).</li>
    <li>💡 Modelos ligeros con tráfico esporádico: SageMaker Serverless o AWS Lambda.</li>
</ul>

<h3>✅ Almacenamiento eficiente</h3>
<p>Los datos crudos pueden quedarse en S3 Standard, pero los modelos antiguos o datasets históricos pueden moverse a S3 Glacier (archivo frío), reduciendo costos drásticamente.</p>

<hr>

<h2>Práctica recomendada: Configuración segura y eficiente</h2>
<p>Como ejercicio práctico, te recomendamos seguir estos pasos:</p>
<ol>
    <li>✅ Crear políticas IAM específicas para SageMaker, S3 y Glue (Principio de Menor Privilegio).</li>
    <li>✅ Configurar cifrado automático en los buckets de S3.</li>
    <li>✅ Crear un modelo y desplegarlo usando una Spot Instance.</li>
    <li>✅ Programar un evento Lambda para pausar el endpoint fuera de horario laboral.</li>
    <li>✅ Analizar el costo total del pipeline usando <a href="https://aws.amazon.com/cost-management/" target="_blank">Cost Explorer</a>.</li>
</ol>

<hr>

<h2>Checklist de Seguridad y Costos</h2>
<p>Antes de cerrar un proyecto de ML en AWS, revisa esta lista:</p>
<ul>
    <li>☑️ ¿Usas roles con permisos mínimos?</li>
    <li>☑️ ¿Cifras datos sensibles?</li>
    <li>☑️ ¿Tienes control de acceso granular en el Data Lake?</li>
    <li>☑️ ¿Optimizaste instancias de entrenamiento?</li>
    <li>☑️ ¿Analizas tus costos regularmente?</li>
    <li>☑️ ¿Automatizas apagado de endpoints?</li>
</ul>

<hr>

<h2>Enlaces útiles</h2>
<ul>
    <li><a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html" target="_blank">Introducción a AWS IAM</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/security.html" target="_blank">Guía de Seguridad en SageMaker</a></li>
    <li><a href="https://aws.amazon.com/sagemaker/pricing/" target="_blank">Precios de SageMaker</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-data-capture.html" target="_blank">Captura de Datos y Monitoreo de Costos</a></li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>En proyectos reales de Machine Learning, seguridad y costos no son opcionales: son factores críticos para el éxito. 
Si proteges tus datos y optimizas recursos desde el inicio, no solo evitarás incidentes, sino que construirás un flujo de trabajo sostenible y escalable.</p>
<p>En el próximo módulo, cerraremos el curso con un repaso general y algunos consejos finales para quienes buscan certificarse o aplicar estos conocimientos en su trabajo diario.</p>
