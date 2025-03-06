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

<p>En cualquier proyecto de IA/ML, uno de los primeros pasos es decidir dónde almacenar los datos. AWS ofrece múltiples opciones, cada una diseñada para diferentes tipos de datos y necesidades.</p>

<hr>

<h3>📂 ¿Qué es un Data Lake?</h3>
<p>Un <strong>Data Lake</strong> es un repositorio central donde se almacenan <strong>todos los datos</strong>, sin importar su formato o estructura. Puede contener:</p>
<ul>
    <li>Datos estructurados (tablas CSV, bases relacionales exportadas).</li>
    <li>Datos semi-estructurados (archivos JSON o XML).</li>
    <li>Datos no estructurados (imágenes, videos, logs).</li>
</ul>
<p>La idea es guardar los datos tal como llegan, sin filtrarlos ni transformarlos de inmediato. Esto permite explorarlos o procesarlos más adelante según las necesidades.</p>

<h4>✅ Amazon S3</h4>
<p><strong>Amazon S3</strong> es el servicio principal para construir Data Lakes en AWS. Es un almacenamiento flexible y económico donde puedes guardar cualquier tipo de archivo.</p>
<p><strong>¿Por qué es clave para IA/ML?</strong></p>
<ul>
    <li>Compatible con todos los formatos.</li>
    <li>Escalable y económico.</li>
    <li>Integrado con Glue, SageMaker, Athena y más.</li>
</ul>

<hr>

<h3>📊 ¿Qué es un Almacén Analítico (Data Warehouse)?</h3>
<p>Un <strong>Data Warehouse</strong> es un almacén optimizado para <strong>consultas SQL complejas</strong> sobre grandes volúmenes de datos <strong>estructurados</strong>.</p>
<p>A diferencia de un Data Lake (que almacena datos crudos), un Data Warehouse requiere que los datos estén previamente procesados y organizados en tablas con un esquema fijo.</p>

<h4>✅ Amazon Redshift</h4>
<p><strong>Amazon Redshift</strong> es el almacén analítico de AWS, ideal cuando necesitas:</p>
<ul>
    <li>Analizar datos históricos en detalle.</li>
    <li>Crear dashboards o reportes con SQL.</li>
    <li>Realizar agregaciones y análisis exploratorios avanzados antes de entrenar un modelo.</li>
</ul>

<hr>

<h3>📋 ¿Qué es una Base de Datos Relacional?</h3>
<p>Una <strong>base de datos relacional</strong> organiza los datos en tablas conectadas entre sí (por ejemplo, una tabla de clientes vinculada a una tabla de pedidos).</p>
<p>Estas bases son ideales para aplicaciones transaccionales, como sistemas de ventas, donde cada registro tiene una relación directa con otros registros.</p>

<h4>✅ Amazon RDS</h4>
<p><strong>Amazon RDS</strong> es el servicio gestionado de bases de datos relacionales en AWS (MySQL, PostgreSQL, SQL Server, entre otros).</p>
<p><strong>¿Por qué es relevante para IA/ML?</strong></p>
<ul>
    <li>Si los datos de entrenamiento provienen de un sistema de ventas o un CRM, probablemente están en RDS.</li>
    <li>RDS facilita exportar estos datos a S3 para crear datasets de entrenamiento.</li>
</ul>

<hr>

<h3>🔐 ¿Qué es la Gobernanza de un Data Lake?</h3>
<p>A medida que el Data Lake crece, es necesario controlar quién accede a qué datos, documentar qué datasets existen y aplicar políticas de seguridad.</p>

<h4>✅ AWS Lake Formation</h4>
<p><strong>AWS Lake Formation</strong> es el servicio que permite:</p>
<ul>
    <li>Definir permisos de acceso a nivel de tabla, columna o fila.</li>
    <li>Crear un catálogo central de datasets.</li>
    <li>Asegurar que cada equipo acceda solo a los datos relevantes para su trabajo.</li>
</ul>
<p>Esto es clave en empresas donde el mismo Data Lake es usado por diferentes áreas: ciencia de datos, finanzas, marketing, etc.</p>

<hr>

<h2>Comparación rápida</h2>
<table border="1">
<tr>
    <th>Servicio</th>
    <th>Tipo de datos</th>
    <th>Casos de uso</th>
</tr>
<tr>
    <td>Amazon S3</td>
    <td>Cualquier formato</td>
    <td>Data Lake - Almacenamiento flexible y económico</td>
</tr>
<tr>
    <td>Amazon Redshift</td>
    <td>Datos estructurados</td>
    <td>Almacén analítico - Análisis SQL complejo</td>
</tr>
<tr>
    <td>Amazon RDS</td>
    <td>Datos relacionales</td>
    <td>Base transaccional - Sistemas operacionales</td>
</tr>
<tr>
    <td>AWS Lake Formation</td>
    <td>Metadatos y permisos</td>
    <td>Gobernanza centralizada del Data Lake</td>
</tr>
</table>

<hr>

<h2>Conclusión</h2>
<p>No existe un único repositorio "correcto". La clave es entender las fortalezas de cada servicio y combinarlos según las necesidades de tu proyecto:</p>
<ul>
    <li>📂 <strong>Amazon S3:</strong> Guardar datos crudos o semi-procesados.</li>
    <li>📊 <strong>Amazon Redshift:</strong> Consultar grandes volúmenes de datos ya transformados.</li>
    <li>📋 <strong>Amazon RDS:</strong> Manejar operaciones transaccionales (datos vivos).</li>
    <li>🔐 <strong>AWS Lake Formation:</strong> Controlar quién accede a qué.</li>
</ul>

<p>Con estos conceptos claros, estás listo para construir pipelines que no solo mueven datos, sino que garantizan calidad, seguridad y eficiencia.</p>


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

