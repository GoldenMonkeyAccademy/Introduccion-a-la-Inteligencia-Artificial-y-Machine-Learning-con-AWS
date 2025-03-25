<h1>Módulo 9: Preparación para la Certificación AWS</h1>

<h2>Objetivo</h2>
<p>En este último módulo consolidaremos todos los conceptos clave aprendidos a lo largo del curso. Además, revisaremos el enfoque específico que utiliza AWS para evaluar tus conocimientos en el examen <strong>AWS Certified Machine Learning - Specialty (MLS-C01)</strong>.</p>

<hr>

<h2>¿Qué es la certificación AWS Certified Machine Learning - Specialty?</h2>
<p>La certificación <strong>AWS MLS-C01</strong> valida que tienes experiencia y conocimiento práctico para diseñar, entrenar, ajustar, desplegar y operar soluciones de Machine Learning en la nube de AWS. 
Es una certificación de nivel <strong>Specialty</strong>, lo que significa que es avanzada y requiere conocimientos previos en AWS y en Machine Learning.</p>

<hr>

<h2>Formato General del Examen</h2>
<ul>
    <li>📄 <strong>Cantidad de preguntas:</strong> 65 preguntas.</li>
    <li>⏱️ <strong>Duración:</strong> 180 minutos (3 horas).</li>
    <li>🌐 <strong>Formato:</strong> Examen en línea (proctored) o presencial en centro autorizado Pearson VUE.</li>
    <li>🗣️ <strong>Idioma:</strong> Disponible en inglés, español, japonés, coreano y chino.</li>
    <li>💰 <strong>Costo:</strong> 300 USD (con posibles descuentos usando vouchers o créditos de entrenamiento).</li>
</ul>

<hr>

<h2>Estructura y Temas Clave de la Certificación</h2>
<p>El examen AWS MLS-C01 evalúa no solo conocimientos teóricos, sino tu habilidad práctica para aplicar Machine Learning usando servicios de AWS. 
Aproximadamente, el contenido se divide así:</p>
<ul>
    <li>📊 <strong>Ingeniería de datos (20%):</strong> Crear pipelines, limpiar datos, preparar datasets.</li>
    <li>🤖 <strong>Modeling (36%):</strong> Selección de algoritmos, entrenar modelos, evaluar desempeño.</li>
    <li>🚀 <strong>Implementación y operaciones (20%):</strong> Desplegar y monitorear modelos.</li>
    <li>🔐 <strong>Seguridad y gobernanza (24%):</strong> IAM, cifrado, control de acceso y optimización de costos.</li>
</ul>

<hr>

<h2>Tipos de preguntas en el examen</h2>
<ul>
    <li>✅ Casos prácticos reales (escenarios tipo empresa).</li>
    <li>✅ Preguntas de selección múltiple (una o varias respuestas correctas).</li>
    <li>✅ Preguntas sobre pipelines completos (end-to-end).</li>
</ul>

<hr>

<h2>Temas Clave que Siempre Aparecen</h2>
<h3>✅ Buenas prácticas en pipelines de datos</h3>
<ul>
    <li>💧 Limpieza y transformación de datos con AWS Glue.</li>
    <li>📥 Ingesta de datos desde Kinesis o S3.</li>
    <li>📊 Diferencias clave entre Athena, Redshift, RDS y S3.</li>
</ul>

<h3>✅ Selección de algoritmos en AWS</h3>
<ul>
    <li>📂 Cuándo usar XGBoost, Random Forest o Deep Learning.</li>
    <li>⚙️ Cómo funciona SageMaker Autopilot.</li>
    <li>🤖 Clasificación, regresión, clustering y refuerzo.</li>
</ul>

<h3>✅ Seguridad y Costos en ML</h3>
<ul>
    <li>🔐 Configuración de roles y permisos (IAM).</li>
    <li>💸 Uso de Spot Instances para entrenamientos.</li>
    <li>📊 Monitoreo de costos y desempeño con CloudWatch y Cost Explorer.</li>
</ul>

<hr>

<h2>Simulacro Corto (Ejemplo)</h2>
<ol>
    <li><strong>¿Cuál es el mejor servicio para crear un pipeline ETL serverless?</strong>
        <ul>
            <li>A) AWS Lambda</li>
            <li>B) AWS Glue</li>
            <li>C) SageMaker Processing</li>
            <li>D) CloudFormation</li>
        </ul>
    </li>
    <li><strong>Tu modelo tiene alta precisión pero bajo recall. ¿Qué significa?</strong>
        <ul>
            <li>A) Detecta muchos falsos negativos.</li>
            <li>B) Detecta muchos falsos positivos.</li>
            <li>C) Está perfectamente balanceado.</li>
            <li>D) No hay suficiente data.</li>
        </ul>
    </li>
    <li><strong>¿Cómo capturar el tráfico de predicciones en un endpoint SageMaker?</strong>
        <ul>
            <li>A) CloudTrail</li>
            <li>B) CloudWatch Logs</li>
            <li>C) Data Capture Config</li>
            <li>D) Lambda Trigger</li>
        </ul>
    </li>
    <li><strong>¿Qué instancia elegirías para entrenar un modelo con 50GB de datos tabulares?</strong>
        <ul>
            <li>A) ml.t3.medium</li>
            <li>B) ml.p3.2xlarge</li>
            <li>C) ml.m5.large con Spot Instances</li>
            <li>D) Lambda</li>
        </ul>
    </li>
    <li><strong>¿Qué algoritmo es mejor para clusterizar clientes sin etiquetas?</strong>
        <ul>
            <li>A) XGBoost</li>
            <li>B) Regresión Logística</li>
            <li>C) K-Means</li>
            <li>D) ARIMA</li>
        </ul>
    </li>
</ol>

<hr>

<h2>Tips Finales</h2>
<ul>
    <li>✅ <strong>Lee la documentación oficial:</strong> AWS siempre evalúa según sus propias guías.</li>
    <li>✅ <strong>Practica en AWS Free Tier:</strong> No basta con leer, tienes que crear pipelines reales.</li>
    <li>✅ <strong>No memorices respuestas:</strong> Entiende <strong>por qué</strong> usas cada servicio y cómo encajan en un flujo completo.</li>
</ul>

<h2>Plan Sugerido de Estudio Final</h2>
<table border="1">
<tr><th>Día</th><th>Actividad</th></tr>
<tr><td>Día 1</td><td>Repaso rápido de S3, SageMaker y Glue.</td></tr>
<tr><td>Día 2</td><td>Simulacro completo (40+ preguntas).</td></tr>
<tr><td>Día 3</td><td>Revisión de errores y conceptos débiles.</td></tr>
<tr><td>Día 4</td><td>Lectura de documentación oficial.</td></tr>
<tr><td>Día 5</td><td>Practicar creando un pipeline real (S3 + Glue + SageMaker).</td></tr>
<tr><td>Día 6</td><td>Último simulacro y checklist final.</td></tr>
</table>

<hr>

<h2>Enlaces Útiles</h2>
<ul>
    <li><a href="https://aws.amazon.com/certification/certified-machine-learning-specialty/" target="_blank">AWS MLS-C01 - Página Oficial</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/" target="_blank">Documentación SageMaker</a></li>
    <li><a href="https://docs.aws.amazon.com/glue/" target="_blank">Documentación Glue</a></li>
    <li><a href="https://tutorialsdojo.com/aws-certified-machine-learning-specialty/" target="_blank">Tutorials Dojo - Exámenes de práctica</a></li>
</ul>

<hr>

<h2>Conclusión Final</h2>
<p>¡Felicidades! Has completado este curso intensivo de Machine Learning en AWS. Más allá de prepararte para la certificación, ahora tienes un conocimiento práctico sólido para crear proyectos reales de IA en la nube. 
Recuerda: <strong>la mejor forma de aprender es aplicando</strong>.</p>
<p>¡Éxito en tu camino como profesional de IA en AWS!</p>
