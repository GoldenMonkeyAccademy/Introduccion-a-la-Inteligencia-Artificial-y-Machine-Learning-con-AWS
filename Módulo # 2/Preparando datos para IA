<h1>Módulo 2: Preparando datos para IA/ML</h1>

<h2>Objetivo</h2>
<p>En este módulo aprenderás por qué los datos son el alma de cualquier proyecto de Machine Learning, cómo evaluar la calidad de un dataset y qué opciones ofrece AWS para crear repositorios y pipelines de datos eficientes. 
Al final, crearás tu primer pipeline real de datos en AWS, combinando almacenamiento, ingesta y procesamiento.</p>

<hr>

<section>
  <h2>¿Qué es un buen dataset para IA/ML?</h2>
  <p>Un modelo es tan bueno como los datos con los que lo entrenas. Por eso, entender qué hace que un dataset sea útil es <strong>crítico</strong>. A continuación, te explicamos las características clave de un buen dataset, junto con ejemplos concretos:</p>

  <h3>✅ Calidad</h3>
  <ul>
    <li><strong>Buen ejemplo:</strong> Dataset de clientes con fechas de nacimiento válidas, sin duplicados, y campos completos como nombre, correo e historial de compras.</li>
    <li><strong>Mal ejemplo:</strong> Fechas como “32/13/2022”, correos faltantes o clientes registrados varias veces con variaciones en el nombre.</li>
  </ul>

  <h3>✅ Volumen</h3>
  <ul>
    <li><strong>Buen ejemplo:</strong> 50,000 transacciones de e-commerce para entrenar un modelo de recomendaciones.</li>
    <li><strong>Mal ejemplo:</strong> Solo 80 registros: el modelo no generaliza y se sobreajusta fácilmente.</li>
  </ul>

  <h3>✅ Variedad</h3>
  <ul>
    <li><strong>Buen ejemplo:</strong> Datos de ventas, clima e inventario combinados para predecir la demanda en supermercados.</li>
    <li><strong>Mal ejemplo:</strong> Solo usar historial de ventas sin considerar promociones o eventos especiales.</li>
  </ul>

  <h3>✅ Representatividad</h3>
  <ul>
    <li><strong>Buen ejemplo:</strong> Datos de fraude de múltiples países, monedas y tipos de transacciones.</li>
    <li><strong>Mal ejemplo:</strong> Entrenar solo con datos de un país y esperar resultados globales.</li>
  </ul>

  <h3>✅ Actualización</h3>
  <ul>
    <li><strong>Buen ejemplo:</strong> Sistema de recomendaciones que se entrena diariamente con interacciones recientes.</li>
    <li><strong>Mal ejemplo:</strong> Datos de hace 3 años usados para detectar fraudes actuales.</li>
  </ul>

  <p><strong>💡 Recuerda:</strong> <em>Garbage In, Garbage Out.</em> No importa cuán avanzado sea tu algoritmo: un mal dataset generará malos resultados.</p>
</section>


<hr>

<h2>Crear repositorios de datos en AWS</h2>

<h3>¿Qué es un Data Lake?</h3>
<p>Un <strong>Data Lake</strong> es un repositorio central donde se almacenan <strong>todos los datos</strong>, sin importar su formato o estructura. Puede contener:</p>
<ul>
    <li>Datos estructurados (tablas CSV, bases relacionales exportadas).</li>
    <li>Datos semi-estructurados (archivos JSON o XML).</li>
    <li>Datos no estructurados (imágenes, videos, logs).</li>
</ul>
<p>La idea es guardar los datos tal como llegan, sin filtrarlos ni transformarlos de inmediato. Esto permite explorarlos o procesarlos más adelante según las necesidades.</p>

<hr>

<h2>Amazon S3: El corazón del Data Lake</h2>
<p><strong>Amazon S3</strong> es el servicio central para construir Data Lakes en AWS. Almacena datos crudos, datos procesados, modelos entrenados y artefactos de ML.</p>

<h3>¿Por qué es clave para IA/ML?</h3>
<ul>
    <li>✅ Flexibilidad: soporta múltiples formatos: CSV, JSON, Parquet, imágenes, videos.</li>
    <li>✅ Escalabilidad: almacena petabytes sin preocuparse por límites.</li>
    <li>✅ Integración: es compatible con SageMaker, Glue, Athena y más.</li>
</ul>

<h3>Clases de almacenamiento</h3>
<table border="1" cellpadding="5" cellspacing="0">
    <thead>
        <tr>
            <th>Clase</th>
            <th>Descripción</th>
            <th>Casos de uso</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>S3 Standard</td>
            <td>Alta disponibilidad y durabilidad.</td>
            <td>Datos activos o en uso frecuente.</td>
        </tr>
        <tr>
            <td>S3 Intelligent-Tiering</td>
            <td>Mueve datos automáticamente entre caliente y frío.</td>
            <td>Datos con patrones de acceso impredecibles.</td>
        </tr>
        <tr>
            <td>S3 Standard-IA</td>
            <td>Para datos accedidos esporádicamente.</td>
            <td>Backups recientes o históricos.</td>
        </tr>
        <tr>
            <td>S3 Glacier Instant Retrieval</td>
            <td>Archivos fríos pero con acceso rápido.</td>
            <td>Datos antiguos, consultas ocasionales.</td>
        </tr>
        <tr>
            <td>S3 Glacier Deep Archive</td>
            <td>Almacenamiento más barato.</td>
            <td>Archivos regulatorios o históricos.</td>
        </tr>
    </tbody>
</table>

<h3>Lifecycle Rules</h3>
<p>Con <strong>Lifecycle Rules</strong>, S3 mueve automáticamente objetos entre clases o los elimina tras cierto tiempo. Ejemplo:</p>
<ul>
    <li>🔄 Mover datos crudos a Glacier tras 90 días.</li>
    <li>🗑️ Eliminar archivos temporales tras 30 días.</li>
</ul>

<h3>Seguridad: Bucket Policies y Cifrado</h3>
<p>Todo bucket debe tener reglas claras de acceso. Con <strong>Bucket Policies</strong>, defines:</p>
<ul>
    <li>Quién puede leer o escribir.</li>
    <li>Qué servicios acceden (ej: solo SageMaker o Glue).</li>
    <li>Permitir o bloquear acceso público.</li>
</ul>

<p>Además, S3 permite cifrado automático:</p>
<ul>
    <li>SSE-S3 (cifrado gestionado por AWS).</li>
    <li>SSE-KMS (cifrado con claves de cliente en AWS KMS).</li>
    <li>Cifrado lado cliente (subir archivos ya cifrados).</li>
</ul>

<h3>VPC Endpoints</h3>
<p>Si tus notebooks o pipelines corren dentro de una VPC privada, usa un <strong>VPC Endpoint</strong> para conectarte a S3 sin pasar por Internet pública.</p>

<hr>

<h2>Otros servicios clave de Data Engineering en AWS</h2>

<h3>Amazon Kinesis Data Streams</h3>
<p><strong>¿Qué es?</strong></p>
<p>Servicio diseñado para la ingesta de datos en tiempo real. Permite capturar flujos continuos de datos, como logs, clics web, métricas de sensores IoT o eventos financieros.</p>
<p><strong>Casos de uso:</strong></p>
<ul>
    <li>Procesar logs de servidores web en tiempo real.</li>
    <li>Analizar clics y comportamiento de usuarios mientras navegan en una app.</li>
    <li>Capturar datos de sensores IoT (temperatura, humedad, etc.).</li>
</ul>
<p><strong>¿Por qué es relevante para IA/ML?</strong></p>
<p>Al capturar datos en tiempo real, puedes alimentar modelos de detección de fraudes, recomendación o mantenimiento predictivo con información fresca y actualizada.</p>

<hr>

<h3>Amazon Kinesis Data Firehose</h3>
<p><strong>¿Qué es?</strong></p>
<p>Un servicio completamente gestionado que toma datos en streaming y los entrega directamente a S3, Redshift o OpenSearch, sin necesidad de escribir código adicional.</p>
<p><strong>Casos de uso:</strong></p>
<ul>
    <li>Capturar logs y guardarlos automáticamente en S3.</li>
    <li>Alimentar un Data Lake con datos crudos desde Firehose.</li>
    <li>Indexar logs en OpenSearch para análisis de seguridad.</li>
</ul>
<p><strong>¿Por qué es relevante para IA/ML?</strong></p>
<p>Permite construir pipelines de datos sin servidores y sin código, asegurando que los datos lleguen a S3 o Redshift listos para ser usados en modelos.</p>

<hr>

<h3>Amazon Managed Service for Apache Flink</h3>
<p><strong>¿Qué es?</strong></p>
<p>Servicio gestionado para ejecutar aplicaciones de procesamiento de datos en streaming usando Apache Flink.</p>
<p><strong>Casos de uso:</strong></p>
<ul>
    <li>Calcular métricas o KPIs en tiempo real.</li>
    <li>Detectar patrones complejos (análisis de series temporales).</li>
    <li>Enriquecer streams con datos históricos.</li>
</ul>
<p><strong>¿Por qué es relevante para IA/ML?</strong></p>
<p>Cuando tus modelos dependen de datos en movimiento (por ejemplo, detección de fraudes o análisis de logs), Flink permite transformar y enriquecer esos datos antes de alimentar al modelo.</p>

<hr>

<h3>AWS Glue</h3>
<p><strong>¿Qué es?</strong></p>
<p>Servicio serverless de ETL (Extract, Transform, Load) que permite limpiar, transformar y mover datos entre fuentes como S3, RDS o Redshift.</p>
<p><strong>Casos de uso:</strong></p>
<ul>
    <li>Transformar datos crudos en S3 a formatos optimizados (Parquet).</li>
    <li>Unir datos de múltiples fuentes (logs de aplicaciones + ventas).</li>
    <li>Limpiar datos eliminando registros duplicados o corruptos.</li>
</ul>
<p><strong>¿Por qué es relevante para IA/ML?</strong></p>
<p>Modelos de Machine Learning solo son tan buenos como los datos que usan. Glue es clave para asegurarte que los datos estén limpios y listos para entrenar modelos.</p>

<hr>

<h3>Glue Data Catalog</h3>
<p><strong>¿Qué es?</strong></p>
<p>Es un catálogo centralizado que almacena el esquema y metadatos de tus datasets, tanto en S3 como en otras fuentes. Es la “biblioteca” que describe dónde están tus datos y cómo se estructuran.</p>
<p><strong>Casos de uso:</strong></p>
<ul>
    <li>Explorar y documentar el Data Lake.</li>
    <li>Permitir que Athena consulte datos de S3.</li>
    <li>Servir como repositorio central de metadatos.</li>
</ul>
<p><strong>¿Por qué es relevante para IA/ML?</strong></p>
<p>Permite que analistas, científicos de datos y modelos accedan a los datos con contexto, sabiendo qué significan cada columna, tipo de dato o tabla.</p>

<hr>

<h3>Glue DataBrew</h3>
<p><strong>¿Qué es?</strong></p>
<p>Herramienta visual sin código para limpiar y preparar datos. Permite realizar transformaciones comunes como eliminar nulos, cambiar formatos o detectar outliers con clics.</p>
<p><strong>Casos de uso:</strong></p>
<ul>
    <li>Limpiar un dataset antes de entrenar un modelo.</li>
    <li>Transformar formatos (de JSON a Parquet).</li>
    <li>Analizar calidad de datos sin escribir código.</li>
</ul>
<p><strong>¿Por qué es relevante para IA/ML?</strong></p>
<p>Ideal para usuarios no técnicos o para realizar exploración rápida antes de un pipeline formal de ETL.</p>

<hr>

<h3>Amazon Athena</h3>
<p><strong>¿Qué es?</strong></p>
<p>Servicio serverless que permite ejecutar consultas SQL directamente sobre datos almacenados en S3. No requiere infraestructura previa.</p>
<p><strong>Casos de uso:</strong></p>
<ul>
    <li>Analizar datasets crudos antes de entrenar modelos.</li>
    <li>Validar resultados de pipelines ETL.</li>
    <li>Crear reportes ad-hoc sobre datos en S3.</li>
</ul>
<p><strong>¿Por qué es relevante para IA/ML?</strong></p>
<p>Te permite explorar y entender tus datos antes de pasarlos al modelo, ayudando a descubrir patrones o problemas de calidad.</p>

<hr>

<h3>AWS Step Functions</h3>
<p><strong>¿Qué es?</strong></p>
<p>Servicio de orquestación que permite coordinar múltiples servicios de AWS en flujos visuales (workflows), ideal para pipelines completos de datos.</p>
<p><strong>Casos de uso:</strong></p>
<ul>
    <li>Pipeline completo: ingesta, transformación, entrenar modelo.</li>
    <li>Automatizar flujos de validación de datos.</li>
    <li>Coordinar tareas entre Lambda, Glue y SageMaker.</li>
</ul>
<p><strong>¿Por qué es relevante para IA/ML?</strong></p>
<p>Los proyectos de ML reales no son tareas aisladas. Con Step Functions, defines todo el flujo de trabajo, garantizando orden y control.</p>

<hr>

<h3>AWS DMS (Database Migration Service)</h3>
<p><strong>¿Qué es?</strong></p>
<p>Servicio que migra datos desde bases on-premises hacia AWS, o entre bases dentro de AWS. Soporta migraciones heterogéneas (Oracle a PostgreSQL, por ejemplo).</p>
<p><strong>Casos de uso:</strong></p>
<ul>
    <li>Migrar datos históricos desde un Oracle local hacia S3.</li>
    <li>Mover bases transaccionales desde MySQL a Aurora.</li>
    <li>Replicar cambios en tiempo real desde una base productiva a un Data Lake.</li>
</ul>
<p><strong>¿Por qué es relevante para IA/ML?</strong></p>
<p>Muchas veces los datos para entrenar modelos provienen de bases existentes. DMS facilita la extracción y sincronización de esos datos hacia AWS.</p>

<hr>

<h2>Práctica: Construir tu primer pipeline de datos</h2>
<ol>
    <li>Crear un bucket S3 llamado "ml-curso-datos".</li>
    <li>Subir ventas.csv.</li>
    <li>Crear trigger S3 que llame a Lambda.</li>
    <li>Lambda valida y lanza Glue.</li>
    <li>Glue transforma y guarda en "ml-curso-datos-limpiados".</li>
    <li>Consultar con Athena.</li>
</ol>

<hr>

<h2>Conclusión</h2>
<p>Sin buenos datos, no hay buen Machine Learning. En AWS, S3 es el corazón del Data Lake, y servicios como Glue, Athena y Kinesis complementan el ecosistema.</p>
<p>En el próximo módulo, aprenderemos a explorar y limpiar estos datos antes de entrenar un modelo.</p>
