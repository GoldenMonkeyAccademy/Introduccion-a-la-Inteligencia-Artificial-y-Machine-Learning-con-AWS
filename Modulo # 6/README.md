<h1>Módulo 6: Despliegue y Monitoreo de Modelos</h1>

<h2>Objetivo</h2>
<p>Aprenderás a desplegar un modelo como endpoint de API y a monitorear su desempeño en producción.</p>

<hr>

<h2>Opciones de Despliegue</h2>
<ul>
    <li>✅ SageMaker Endpoint (recomendado para modelos ML).</li>
    <li>✅ Lambda (ideal para modelos ligeros).</li>
    <li>✅ Fargate (útil para modelos más pesados en contenedores).</li>
</ul>

<pre><code>
predictor = xgb.deploy(instance_type='ml.m5.large', endpoint_name='mi-modelo')
</code></pre>

<hr>

<h2>Monitoreo y Alerta</h2>
<p>Con SageMaker Model Monitor y CloudWatch, puedes detectar problemas de deriva y cambios en la calidad de los datos.</p>

<hr>

<h2>Práctica: Despliegue y Monitoreo</h2>
<ul>
    <li>✅ Desplegar modelo como endpoint.</li>
    <li>✅ Hacer predicciones desde Python o Postman.</li>
    <li>✅ Configurar monitoreo con Model Monitor.</li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>Tu modelo ahora está en producción. El siguiente paso es asegurar seguridad y controlar costos.</p>
