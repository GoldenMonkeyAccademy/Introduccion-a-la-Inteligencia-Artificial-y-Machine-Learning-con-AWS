<h1>Módulo 3: Exploración y Limpieza de Datos para Machine Learning</h1>

<h2>Objetivo</h2>
<p>En este módulo aprenderás a explorar, entender y limpiar datos usando herramientas de AWS y Python. 
La exploración de datos es un paso clave para identificar problemas de calidad, entender patrones iniciales y tomar decisiones sobre qué atributos son más relevantes para tu modelo.</p>

<hr>

<h2>¿Por qué es clave la exploración de datos?</h2>
<p>Antes de entrenar cualquier modelo, es vital conocer tus datos. 
Si entrenas un modelo sin revisar los datos, es como cocinar sin leer los ingredientes. Una buena exploración permite:</p>
<ul>
    <li>✅ Detectar datos faltantes o inconsistentes.</li>
    <li>✅ Conocer distribuciones y valores atípicos.</li>
    <li>✅ Visualizar relaciones entre variables.</li>
    <li>✅ Evaluar la necesidad de transformación o escalado.</li>
</ul>
<p>En este módulo, usaremos herramientas como <strong>Pandas</strong>, <strong>Matplotlib</strong>, <strong>Seaborn</strong> y <strong>Amazon Athena</strong> para hacer esta exploración, combinando lo mejor de Python con AWS.</p>

<hr>

<h2>Primer paso: Cargar datos en un Notebook</h2>
<p>Para explorar datos, primero hay que cargarlos. En AWS, puedes hacerlo de varias formas:</p>
<ul>
    <li>📂 Cargar directamente desde un archivo CSV en S3 usando Pandas.</li>
    <li>📊 Consultar los datos desde Redshift o Athena y leerlos como DataFrame.</li>
    <li>🔗 Usar Data Wrangler de SageMaker, que conecta múltiples fuentes y ya incluye herramientas visuales de exploración.</li>
</ul>

<p><strong>Ejemplo básico:</strong> Leer un CSV desde S3</p>
<pre><code>
import pandas as pd
import boto3

s3 = boto3.client('s3')
bucket = 'ml-curso-datos-limpiados'
key = 'ventas_procesadas.csv'

response = s3.get_object(Bucket=bucket, Key=key)
df = pd.read_csv(response['Body'])

df.head()
</code></pre>

<hr>

<h2>Revisar la calidad de los datos</h2>
<p>Una vez cargados, es hora de revisar:</p>
<ul>
    <li>✔️ Cantidad de registros y columnas.</li>
    <li>✔️ Tipos de datos (numéricos, categóricos, fechas).</li>
    <li>✔️ Datos faltantes o nulos.</li>
    <li>✔️ Valores extremos (outliers).</li>
    <li>✔️ Distribuciones.</li>
</ul>

<p><strong>Ejemplos:</strong></p>
<pre><code>
df.info()
df.describe()
df.isnull().sum()
</code></pre>

<hr>

<h2>Visualizar para entender mejor</h2>
<p>Las gráficas ayudan a descubrir patrones ocultos. Algunas visualizaciones clave:</p>
<ul>
    <li>📊 Histogramas para ver distribuciones.</li>
    <li>📉 Boxplots para detectar outliers.</li>
    <li>📈 Scatter plots para ver correlaciones.</li>
    <li>📊 Heatmaps para ver correlaciones entre variables.</li>
</ul>

<p><strong>Ejemplo:</strong> Histograma de ventas</p>
<pre><code>
import matplotlib.pyplot as plt

plt.hist(df['ventas'], bins=20)
plt.title('Distribución de ventas')
plt.show()
</code></pre>

<hr>

<h2>Limpieza de datos</h2>
<p>Luego de explorar, es momento de limpiar:</p>
<ul>
    <li>💧 Eliminar columnas irrelevantes.</li>
    <li>💧 Completar o eliminar datos faltantes.</li>
    <li>💧 Corregir tipos de datos.</li>
    <li>💧 Crear nuevas variables (feature engineering).</li>
</ul>

<p><strong>Ejemplos:</strong></p>
<pre><code>
# Eliminar columna irrelevante
df = df.drop(columns=['columna_inutil'])

# Llenar datos faltantes
df['precio'].fillna(df['precio'].median(), inplace=True)

# Crear columna nueva
df['precio_m2'] = df['precio'] / df['metros_cuadrados']
</code></pre>

<hr>

<h2>Práctica: Exploración y limpieza de un dataset real</h2>
<p>Para esta práctica, trabajaremos con un dataset de ventas que subimos a S3 en el módulo anterior. Los pasos serán:</p>
<ol>
    <li>Leer el dataset directamente desde S3 usando Pandas.</li>
    <li>Analizar estructura, tipos de datos y valores faltantes.</li>
    <li>Visualizar la distribución de algunas variables clave.</li>
    <li>Limpiar datos inconsistentes o duplicados.</li>
    <li>Crear nuevas variables útiles (por ejemplo, precio/m2).</li>
</ol>

<p><strong>Enlaces útiles:</strong></p>
<ul>
    <li><a href="https://pandas.pydata.org/docs/index.html" target="_blank">Documentación oficial de Pandas</a></li>
    <li><a href="https://matplotlib.org/stable/contents.html" target="_blank">Documentación oficial de Matplotlib</a></li>
    <li><a href="https://seaborn.pydata.org/" target="_blank">Documentación oficial de Seaborn</a></li>
    <li><a href="https://docs.aws.amazon.com/athena/latest/ug/what-is.html" target="_blank">Introducción a Amazon Athena</a></li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>En Machine Learning, el 80% del trabajo suele estar en preparar los datos. Un buen análisis exploratorio no solo mejora la calidad de los modelos, 
sino que permite entender mejor el problema y comunicar hallazgos de forma clara.</p>
<p>En el próximo módulo, usaremos estos datos ya limpios para seleccionar algoritmos y crear nuestro primer modelo de Machine Learning.</p>
