

<h1>Módulo 3: Exploración y Limpieza de Datos para Machine Learning</h1>

<h2>Objetivo</h2>
<p>En este módulo aprenderás a explorar, entender y limpiar datos usando herramientas de AWS y Python. Este proceso es crucial para cualquier proyecto de Machine Learning, ya que la calidad de tus datos define directamente el desempeño de tu modelo.</p>

<hr>

<h2>¿Qué es la exploración de datos?</h2>
<p>Explorar datos significa entender cómo son, qué información contienen, detectar errores o valores atípicos, y descubrir patrones iniciales. Sin un buen análisis exploratorio, cualquier modelo que entrenes será una caja negra sin contexto.</p>

<h3>¿Por qué es clave la exploración?</h3>
<ul>
    <li>✅ Detectar datos faltantes, duplicados o inconsistentes.</li>
    <li>✅ Conocer distribuciones, sesgos y valores extremos (outliers).</li>
    <li>✅ Identificar correlaciones y relaciones entre variables.</li>
    <li>✅ Evaluar si necesitas transformar o escalar variables.</li>
</ul>

<h3>Herramientas clave</h3>
<p>Para explorar datos, usaremos:</p>
<ul>
    <li>📊 Pandas (manipulación de datos).</li>
    <li>📈 Matplotlib y Seaborn (visualizaciones).</li>
    <li>🔎 Amazon Athena (consultas SQL sobre S3).</li>
</ul>

<hr>

<h2>Tipos de Datos</h2>
<p>Identificar correctamente el tipo de dato es fundamental para elegir las técnicas de limpieza y visualización adecuadas:</p>
<ul>
    <li><strong>Estructurados:</strong> Datos tabulares (CSV, Excel, SQL).</li>
    <li><strong>Semi-estructurados:</strong> JSON, XML, logs con formato flexible.</li>
    <li><strong>No estructurados:</strong> Imágenes, audio, video, texto libre.</li>
    <li><strong>Series temporales:</strong> Datos con componente temporal, como ventas diarias.</li>
</ul>

<hr>

<h2>Distribuciones de Datos</h2>
<p>Conocer la forma de cada variable te ayuda a decidir transformaciones o técnicas especiales:</p>
<ul>
    <li>📊 <strong>Distribución Normal:</strong> La clásica curva de campana.</li>
    <li>📉 <strong>Sesgada:</strong> Mayor concentración de datos en un extremo.</li>
    <li>📈 <strong>Multimodal:</strong> Más de un pico o concentración.</li>
</ul>

<hr>

<h2>Series Temporales: Tendencias y Estacionalidad</h2>
<p>Cuando trabajas con datos de ventas, clima o métricas operacionales, es clave identificar:</p>
<ul>
    <li>📈 <strong>Tendencia:</strong> Crecimiento o caída general.</li>
    <li>🔄 <strong>Estacionalidad:</strong> Patrones que se repiten (diarios, mensuales).</li>
</ul>

<hr>

<h2>Primer paso: Cargar datos en un Notebook</h2>
<p>Para explorar datos, primero hay que cargarlos. En AWS, puedes hacerlo de varias formas:</p>
<ul>
    <li>📂 Leer directamente desde un archivo CSV en S3 con Pandas.</li>
    <li>📊 Consultar datos directamente desde Redshift o Athena.</li>
    <li>🔗 Usar SageMaker Data Wrangler para cargar, transformar y visualizar datos.</li>
</ul>

<pre><code>
import pandas as pd
import boto3
s3 = boto3.client('s3')
response = s3.get_object(Bucket='ml-curso-datos-limpiados', Key='ventas_procesadas.csv')
df = pd.read_csv(response['Body'])
df.head()
</code></pre>

<hr>

<h2>Chequeo inicial: Evaluar la calidad de los datos</h2>

<p>Antes de comenzar cualquier análisis o entrenamiento, es clave realizar un primer chequeo de calidad sobre el dataset. 
A continuación, te mostramos un ejemplo de dataset y cómo ejecutar cada uno de los puntos clave usando Pandas.</p>

<h3>📊 Ejemplo de dataset (ventas.csv)</h3>
<table border="1" cellpadding="5" cellspacing="0">
    <tr>
        <th>fecha</th>
        <th>cliente_id</th>
        <th>producto</th>
        <th>cantidad</th>
        <th>precio_unitario</th>
        <th>metodo_pago</th>
    </tr>
    <tr><td>2024-03-01</td><td>C001</td><td>Laptop</td><td>1</td><td>1200</td><td>Tarjeta</td></tr>
    <tr><td>2024-03-01</td><td>C002</td><td>Mouse</td><td>2</td><td>25</td><td>Efectivo</td></tr>
    <tr><td>2024-03-02</td><td>C001</td><td>Teclado</td><td></td><td>50</td><td>Tarjeta</td></tr>
    <tr><td>2024-03-02</td><td>C003</td><td>Monitor</td><td>1</td><td>300</td><td>Transferencia</td></tr>
    <tr><td>2024-03-03</td><td>C002</td><td>Mouse</td><td>1</td><td>25</td><td>Efectivo</td></tr>
    <tr><td>2024-03-03</td><td>C001</td><td>Teclado</td><td>1</td><td></td><td>Tarjeta</td></tr>
    <tr><td>2024-03-03</td><td>C004</td><td>Silla</td><td>1</td><td>100</td><td>Efectivo</td></tr>
    <tr><td>2024-03-01</td><td>C001</td><td>Laptop</td><td>1</td><td>1200</td><td>Tarjeta</td></tr>
</table>

<h3>✔️ 1. Cantidad de registros y columnas</h3>
<pre><code>
print(f'Cantidad de registros: {df.shape[0]}')
print(f'Cantidad de columnas: {df.shape[1]}')
</code></pre>
<p><strong>Resultado esperado:</strong><br>
Cantidad de registros: 8<br>
Cantidad de columnas: 6
</p>

<h3>✔️ 2. Tipos de datos (numéricos, categóricos, fechas)</h3>
<pre><code>
print(df.dtypes)
</code></pre>
<p><strong>Resultado esperado:</strong></p>
<pre>
fecha               object
cliente_id          object
producto            object
cantidad            float64
precio_unitario     float64
metodo_pago         object
</pre>
<p><strong>Observación:</strong> La columna <code>fecha</code> debería ser tipo <code>datetime</code>, por lo que se debe convertir.</p>

<h3>✔️ 3. Datos faltantes o nulos</h3>
<pre><code>
print(df.isnull().sum())
</code></pre>
<p><strong>Resultado esperado:</strong></p>
<pre>
fecha              0
cliente_id         0
producto           0
cantidad           1
precio_unitario    1
metodo_pago        0
</pre>
<p><strong>Observación:</strong> Hay un registro sin <code>cantidad</code> y otro sin <code>precio_unitario</code>, lo cual es crítico.</p>

<h3>✔️ 4. Registros duplicados</h3>
<pre><code>
print(f'Registros duplicados: {df.duplicated().sum()}')
</code></pre>
<p><strong>Resultado esperado:</strong><br>
Registros duplicados: 1</p>
<p><strong>Observación:</strong> Hay una venta de Laptop duplicada (misma fecha, cliente, producto, etc.).</p>

<h3>✔️ 5. Columnas innecesarias</h3>
<p>El análisis de columnas innecesarias es manual y depende del objetivo. 
En este caso, si el <code>metodo_pago</code> no es relevante para el modelo, podría eliminarse:</p>
<pre><code>
df = df.drop(columns=['metodo_pago'])
</code></pre>

<h3>Resumen final del chequeo inicial</h3>
<table border="1" cellpadding="5" cellspacing="0">
    <tr>
        <th>Concepto</th>
        <th>Resultado</th>
    </tr>
    <tr><td>Registros</td><td>8</td></tr>
    <tr><td>Columnas</td><td>6</td></tr>
    <tr><td>Tipos de datos</td><td>Algunos incorrectos (fecha como object)</td></tr>
    <tr><td>Valores nulos</td><td>cantidad y precio_unitario</td></tr>
    <tr><td>Duplicados</td><td>1 registro</td></tr>
    <tr><td>Columnas innecesarias</td><td>metodo_pago podría eliminarse</td></tr>
</table>

<p>Este análisis inicial es clave para comenzar la limpieza de datos con una visión clara de qué problemas existen en la fuente.</p>

<hr>


<pre><code>
df.info()
df.describe()
df.isnull().sum()
df.duplicated().sum()
</code></pre>

<hr>

<hr>

<h2>📋 Buenas Prácticas y Recomendaciones al Explorar Datos</h2>

<h3>✅ Chequeo inicial: El primer diagnóstico</h3>
<p>Piensa en el chequeo inicial como un "check-up médico" para tus datos. Antes de entrenar cualquier modelo, 
debes conocer el estado actual de tus datos: su calidad, completitud y posibles inconsistencias. 
Este chequeo es obligatorio en cualquier pipeline de datos serio.</p>

<p>Sin este paso, podrías entrenar un modelo sobre datos incompletos, desactualizados o corruptos, 
obteniendo resultados poco fiables o directamente erróneos.</p>

<hr>

<h3>✅ Ejemplos adicionales de columnas innecesarias</h3>
<p>Dependiendo de la naturaleza del proyecto, hay columnas que suelen ser eliminadas porque no aportan valor predictivo:</p>
<ul>
    <li>📑 Notas internas o comentarios.</li>
    <li>🔗 ID de proceso interno (sin relación directa con el target).</li>
    <li>👤 Usuario que cargó el registro (irrelevante para el modelo).</li>
</ul>
<p>Recuerda: si una columna no tiene correlación lógica o estadística con la variable objetivo, 
es candidata para ser eliminada.</p>

<hr>

<h3>✅ Revisión especial de fechas y tiempos</h3>
<p>En datos reales, es muy común que las fechas lleguen mal formateadas o como texto (string). 
Esto dificulta análisis temporales o la creación de features como la edad de un cliente o el tiempo entre eventos.</p>

<pre><code>
df['fecha'] = pd.to_datetime(df['fecha'], errors='coerce')
</code></pre>
<p>Además, es buena práctica graficar la cantidad de registros por día/mes/año para detectar:</p>
<ul>
    <li>📉 Gaps de datos (días sin registros).</li>
    <li>⚠️ Fechas atípicas (años fuera de rango: 1900 o 2100).</li>
</ul>

<hr>

<h3>✅ Revisión de cardinalidad en variables categóricas</h3>
<p>La cardinalidad es la cantidad de valores únicos en una columna. En variables categóricas, 
una cardinalidad excesiva es una alerta de datos sucios o de columnas poco relevantes.</p>
<pre><code>
df['producto'].nunique()
</code></pre>
<p>Recomendación: Si tienes una columna como "nombre_producto" con miles de valores únicos, 
puede ser mejor agruparlos en categorías más amplias (ej. "Electrónica", "Muebles", etc.).</p>

<hr>

<h3>✅ Documenta los problemas encontrados</h3>
<p>Cada hallazgo es valioso. Documentar qué columnas tenían nulos, qué fechas estaban fuera de rango 
o qué columnas fueron eliminadas, crea un histórico útil para auditorías o futuros análisis.</p>

<p>Una buena práctica es tener un archivo <strong>data_quality_report.md</strong> donde registres:</p>
<ul>
    <li>✅ Fecha del análisis.</li>
    <li>✅ Problemas encontrados (nulos, duplicados, formatos incorrectos).</li>
    <li>✅ Soluciones aplicadas (imputación, eliminación de registros, etc.).</li>
</ul>

<hr>

<h3>✅ Automatiza el chequeo inicial</h3>
<p>En proyectos grandes, puedes crear un script estándar (notebook base) que automáticamente:</p>
<ul>
    <li>✅ Carga el dataset.</li>
    <li>✅ Ejecuta df.info(), df.describe(), df.isnull().sum(), etc.</li>
    <li>✅ Genera un pequeño reporte automático (gráficas y métricas).</li>
</ul>
<p>Esto te ahorra tiempo y asegura que todos los datasets reciban la misma revisión de calidad.</p>

<hr>

<h3>📊 Ejemplo gráfico de flujo de trabajo</h3>
<p>Para cerrar, esta es la secuencia ideal al explorar datos:</p>
<ul>
    <li>📂 Carga de datos.</li>
    <li>🔍 Chequeo inicial.</li>
    <li>📊 Visualización exploratoria.</li>
    <li>💧 Limpieza de datos.</li>
    <li>⚒️ Feature Engineering.</li>
</ul>
<p>Cada paso depende del anterior, creando un flujo de trabajo sólido y documentado.</p>

<hr>

<h2>📚 Enlaces recomendados</h2>
<ul>
    <li><a href="https://pandas.pydata.org/docs/" target="_blank">Documentación oficial de Pandas</a></li>
    <li><a href="https://matplotlib.org/stable/contents.html" target="_blank">Documentación de Matplotlib</a></li>
    <li><a href="https://seaborn.pydata.org/" target="_blank">Documentación de Seaborn</a></li>
</ul>
<hr>
<h2>Visualización exploratoria</h2>
<ul>
    <li>📊 Histogramas: distribuciones por variable.</li>
    <li>📉 Boxplots: detección de outliers.</li>
    <li>📈 Scatter plots: relaciones entre variables.</li>
    <li>🔥 Heatmaps: correlaciones entre variables numéricas.</li>
</ul>

<pre><code>
import matplotlib.pyplot as plt
plt.hist(df['ventas'], bins=20)
plt.title('Distribución de Ventas')
plt.show()
</code></pre>

<hr>

<h2>Errores comunes a identificar</h2>
<ul>
    <li>⚠️ Fechas fuera de rango (año 1900 o 2100).</li>
    <li>⚠️ Valores negativos en columnas como precio o edad.</li>
    <li>⚠️ Columnas categóricas con demasiados valores únicos (alta cardinalidad).</li>
    <li>⚠️ Registros duplicados.</li>
</ul>

<pre><code>
df.duplicated().sum()
</code></pre>

<hr>

<h2>Transformación y Feature Engineering</h2>
<ul>
    <li>✅ Convertir categorías a números (encoding).</li>
    <li>✅ Normalizar (Min-Max) o estandarizar (Z-score).</li>
    <li>✅ Crear columnas nuevas (combinaciones o ratios).</li>
</ul>

<pre><code>
df['categoria_precio'] = pd.qcut(df['precio'], q=4, labels=['bajo', 'medio', 'alto', 'muy alto'])
</code></pre>

<hr>

<h2>Práctica</h2>
<p>Con el dataset de ventas en S3, realiza:</p>
<ol>
    <li>Cargar datos.</li>
    <li>Revisar estructura, tipos y nulos.</li>
    <li>Graficar distribuciones clave.</li>
    <li>Limpiar duplicados y errores.</li>
    <li>Crear al menos dos variables nuevas.</li>
</ol>

<hr>

<h2>Conclusión</h2>
<p>Datos limpios son la clave para modelos precisos. En el próximo módulo, entrenaremos el primer modelo.</p>
