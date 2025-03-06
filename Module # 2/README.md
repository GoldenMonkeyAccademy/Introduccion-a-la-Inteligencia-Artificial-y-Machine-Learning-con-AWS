<h1>Módulo 2: Preparando datos para IA/ML</h1>

<h2>Objetivo</h2>
<p>En este módulo aprenderás por qué los datos son el alma de cualquier proyecto de Machine Learning, cómo evaluar la calidad de un dataset y qué opciones ofrece AWS para crear repositorios y pipelines de datos eficientes. 
Al final, crearás tu primer pipeline real de datos en AWS, combinando almacenamiento, ingesta y procesamiento.</p>

<hr>

<h2>¿Qué es un buen dataset para IA/ML?</h2>
<p>Un modelo es tan bueno como los datos con los que lo entrenas. Por eso, entender qué hace que un dataset sea útil es crítico. Un buen dataset tiene:</p>

<ul>
    <li><strong>Calidad:</strong> Datos sin errores (fechas inválidas, campos vacíos, registros duplicados o inconsistentes).</li>
    <li><strong>Volumen:</strong> Suficiente cantidad para representar patrones reales. Un modelo no puede generalizar si tiene muy pocos ejemplos.</li>
    <li><strong>Variedad:</strong> Diversidad de fuentes y formatos, reflejando el entorno real (por ejemplo, combinar datos de ventas con clima).</li>
    <li><strong>Representatividad:</strong> Los datos deben reflejar el fenómeno real. Si entrenas un modelo de fraudes solo con datos de un país, fallará al detectar fraudes globales.</li>
    <li><strong>Actualización:</strong> En casos como detección de fraudes o recomendaciones, es clave que los datos estén frescos.</li>
</ul>

<p><strong>Recuerda:</strong> Garbage In, Garbage Out. Un mal dataset no puede producir un buen modelo, sin importar cuán avanzado sea el algoritmo.</p>

<hr>

<h2>Crear repositorios de datos en AWS</h2>
<p>En AWS, podemos almacenar datos en diferentes servicios, cada uno optimizado para ciertos casos:</p>

<ul>
    <li>✅ <strong>Amazon S3:</strong> Almacenamiento flexible (data lake), perfecto para datos crudos en CSV, JSON, Parquet, imágenes o videos.</li>
    <li>✅ <strong>Amazon Redshift:</strong> Almacén analítico, optimizado para consultar grandes volúmenes de datos estructurados con SQL.</li>
    <li>✅ <strong>Amazon RDS:</strong> Bases de datos relacionales gestionadas (MySQL, PostgreSQL, etc.), ideal para datos transaccionales.</li>
    <li>✅ <strong>AWS Lake Formation:</strong> Servicio para crear un Data Lake completo con control centralizado de permisos.</li>
</ul>

<p><strong>Recomendación práctica:</strong> Para proyectos de IA/ML, la combinación más común es:</p>
<ul>
    <li>💾 Datos crudos → S3</li>
    <li>🔨 Datos transformados → S3 o Redshift</li>
    <li>📊 Consultas exploratorias → Athena o Redshift</li>
</ul>

<p><strong>Diferencia clave:</strong></p>
<ul>
    <li><strong>S3:</strong> Almacenamiento barato y flexible, pero lento para análisis directo.</li>
    <li><strong>Redshift:</strong> Rápido para consultas analíticas complejas, pero más costoso y rígido.</li>
    <li><strong>Athena:</strong> Consultas SQL directas sobre datos en S3 (serverless), ideal para análisis ad-hoc.</li>
</ul>

<hr>

<h2>Pipelines de ingesta en AWS</h2>
<p>En la vida real, los datos no llegan "limpitos" a nuestro repositorio. Hay que extraerlos, limpiarlos, transformarlos y cargarlos. En AWS, podemos armar pipelines con:</p>

<ul>
    <li>✅ <strong>AWS Glue:</strong> Servicio ETL serverless, perfecto para transformar grandes volúmenes de datos, convertir formatos o enriquecer datasets.</li>
    <li>✅ <strong>Amazon Kinesis:</strong> Ingesta de datos en tiempo real, ideal para streams como logs o clics web.</li>
    <li>✅ <strong>AWS Lambda:</strong> Funciones serverless que se ejecutan cuando llega un archivo a S3, para hacer validaciones o transformaciones ligeras.</li>
</ul>

<p><strong>¿Cuándo usar cada uno?</strong></p>
<ul>
    <li><strong>Glue:</strong> Cuando hay volúmenes grandes y transformaciones complejas (unificación de formatos, limpieza, joins).</li>
    <li><strong>Kinesis:</strong> Cuando los datos fluyen constantemente (streams en tiempo real, logs, sensores IoT).</li>
    <li><strong>Lambda:</strong> Para automatizar respuestas a eventos (nuevo archivo llega a S3 → validarlo y moverlo).</li>
</ul>

<p><strong>Ejemplo típico:</strong></p>
<pre>
Cliente sube archivo CSV a S3.
Evento S3 dispara Lambda.
Lambda valida el archivo y lanza Glue.
Glue limpia y transforma los datos.
Datos procesados se guardan en un bucket final o en Redshift.
</pre>

<hr>

<h2>Práctica: Tu primer pipeline de datos en AWS</h2>
<p>Vamos a crear este flujo end-to-end:</p>

<ol>
    <li>Crear un bucket en S3 llamado <code>ml-curso-datos</code>.</li>
    <li>Subir un archivo de muestra (por ejemplo, ventas.csv).</li>
    <li>Configurar un evento de S3 que llame a una Lambda cada vez que llegue un archivo nuevo.</li>
    <li>Crear una Lambda que valide el archivo (estructura, nombres de columnas) y lance un Job de Glue.</li>
    <li>En Glue, crear un script simple que limpia los datos (elimina filas vacías y normaliza formatos).</li>
    <li>Guardar los datos procesados en un bucket final <code>ml-curso-datos-limpiados</code>.</li>
    <li>Opcional: Consultar los datos limpios con Athena.</li>
</ol>

<p><strong>Enlaces útiles:</strong></p>
<ul>
    <li><a href="https://docs.aws.amazon.com/glue/latest/dg/what-is-glue.html" target="_blank">Documentación AWS Glue</a></li>
    <li><a href="https://docs.aws.amazon.com/lambda/latest/dg/getting-started.html" target="_blank">Guía inicial AWS Lambda</a></li>
    <li><a href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html" target="_blank">Introducción Amazon S3</a></li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>En Machine Learning, **los datos son más importantes que los algoritmos**. Un pipeline robusto asegura que tus modelos aprendan de información limpia, fresca y relevante.</p>
<p>En el próximo módulo, aprenderemos cómo explorar, visualizar y limpiar esos datos para convertirlos en insumos perfectos para entrenar modelos.</p>

