<h1>Módulo 3: Exploración y Limpieza de Datos para Machine Learning</h1>

<h2>Objetivo</h2>
<p>En este módulo aprenderás a explorar, entender y limpiar datos usando herramientas de AWS y Python. 
Este proceso es crucial para cualquier proyecto de Machine Learning, ya que la calidad de tus datos define directamente el desempeño de tu modelo.</p>

<hr>

<h2>¿Por qué es clave la exploración de datos?</h2>
<p>Entrenar un modelo sin revisar tus datos es como cocinar sin leer los ingredientes: 
puede funcionar, pero lo más probable es que salga mal. 
La exploración de datos permite:</p>
<ul>
    <li>✅ Detectar datos faltantes, duplicados o inconsistentes.</li>
    <li>✅ Conocer las distribuciones de cada variable.</li>
    <li>✅ Identificar valores extremos (outliers).</li>
    <li>✅ Descubrir relaciones entre variables (correlaciones).</li>
    <li>✅ Evaluar la necesidad de normalizar, escalar o transformar variables.</li>
</ul>

<p><strong>Herramientas clave:</strong> Pandas, Matplotlib, Seaborn y Amazon Athena. Combinaremos lo mejor de Python con el poder de AWS.</p>

<hr>

<h2>Primer paso: Cargar datos en un Notebook</h2>
<p>Para explorar los datos, primero hay que cargarlos. En AWS, hay varias opciones:</p>
<ul>
    <li>📂 Leer directamente desde un archivo CSV en S3 con Pandas.</li>
    <li>📊 Consultar datos directamente desde Redshift o Athena (SQL en la nube).</li>
    <li>🔗 Usar SageMaker Data Wrangler, que facilita cargar, transformar y visualizar datos.</li>
</ul>

<h3>Ejemplo básico: Leer un CSV desde S3</h3>
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
<p>Una vez cargados los datos, comienza el chequeo inicial:</p>
<ul>
    <li>✔️ ¿Cuántas filas y columnas hay?</li>
    <li>✔️ ¿Cuáles son los tipos de datos (numéricos, categóricos, fechas)?</li>
    <li>✔️ ¿Cuántos valores faltantes hay?</li>
    <li>✔️ ¿Existen registros duplicados?</li>
    <li>✔️ ¿Hay columnas irrelevantes?</li>
</ul>

<h3>Comandos clave:</h3>
<pre><code>
df.info()
df.describe()
df.isnull().sum()
df.duplicated().sum()
</code></pre>

<hr>

<h2>Visualización exploratoria</h2>
<p>Las gráficas permiten detectar patrones, distribuciones extrañas y outliers visualmente.</p>
<ul>
    <li>📊 Histogramas: distribuciones por variable.</li>
    <li>📉 Boxplots: detección de outliers.</li>
    <li>📈 Scatter plots: relaciones entre variables.</li>
    <li>🔥 Heatmaps: correlaciones entre variables numéricas.</li>
</ul>

<h3>Ejemplo: Histograma de ventas</h3>
<pre><code>
import matplotlib.pyplot as plt

plt.hist(df['ventas'], bins=20)
plt.title('Distribución de Ventas')
plt.show()
</code></pre>

<hr>

<h2>Errores comunes a identificar</h2>
<p>Al explorar, es común encontrar:</p>
<ul>
    <li>⚠️ Fechas fuera de rango (1900 o 2100).</li>
    <li>⚠️ Valores negativos en variables que no deberían tenerlos (precio, edad).</li>
    <li>⚠️ Columnas categóricas con demasiados valores únicos (cardinalidad alta).</li>
    <li>⚠️ Registros duplicados (mismo cliente y misma fecha).</li>
</ul>

<h3>Detectar duplicados:</h3>
<pre><code>
df.duplicated().sum()
</code></pre>

<hr>

<h2>Limpieza de datos</h2>
<p>Una vez identificados los problemas, es hora de limpiar:</p>
<ul>
    <li>💧 Eliminar columnas irrelevantes o redundantes.</li>
    <li>💧 Completar o eliminar datos faltantes.</li>
    <li>💧 Corregir tipos de datos (fechas como datetime, categorías como strings).</li>
    <li>💧 Crear nuevas variables útiles (feature engineering).</li>
</ul>

<h3>Ejemplos:</h3>
<pre><code>
# Eliminar columna innecesaria
df = df.drop(columns=['columna_inutil'])

# Llenar nulos con la mediana
df['precio'].fillna(df['precio'].median(), inplace=True)

# Crear nueva variable
df['precio_m2'] = df['precio'] / df['metros_cuadrados']
</code></pre>

<hr>

<h2>Transformación y Feature Engineering</h2>
<p>La limpieza no es solo corregir errores. También es preparar los datos para que los modelos trabajen mejor.</p>
<ul>
    <li>✅ Convertir categorías en números (encoding).</li>
    <li>✅ Normalizar o escalar valores.</li>
    <li>✅ Crear nuevas variables (ej. ratios o combinaciones de otras).</li>
</ul>

<h3>Ejemplo: Crear una columna categórica</h3>
<pre><code>
df['categoria_precio'] = pd.qcut(df['precio'], q=4, labels=['bajo', 'medio', 'alto', 'muy alto'])
</code></pre>

<hr>

<h2>Práctica: Exploración y limpieza real</h2>
<p>Te toca poner manos a la obra. Usaremos el dataset de ventas subido a S3 en el Módulo 2. 
Tu reto es completar los siguientes pasos:</p>
<ol>
    <li>📂 Leer dataset desde S3.</li>
    <li>📊 Revisar estructura, tipos y valores nulos.</li>
    <li>📈 Graficar distribuciones y relaciones clave.</li>
    <li>💧 Limpiar datos inconsistentes.</li>
    <li>⚒️ Crear al menos dos nuevas variables derivadas.</li>
</ol>

<h3>Enlaces útiles</h3>
<ul>
    <li><a href="https://pandas.pydata.org/docs/" target="_blank">Documentación oficial de Pandas</a></li>
    <li><a href="https://matplotlib.org/stable/contents.html" target="_blank">Documentación oficial de Matplotlib</a></li>
    <li><a href="https://seaborn.pydata.org/" target="_blank">Documentación oficial de Seaborn</a></li>
    <li><a href="https://docs.aws.amazon.com/athena/latest/ug/what-is.html" target="_blank">Introducción a Amazon Athena</a></li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>En Machine Learning, el 80% del trabajo es preparar datos. 
Un buen análisis exploratorio te ayuda a:</p>
<ul>
    <li>✅ Entender el negocio desde los datos.</li>
    <li>✅ Detectar problemas antes de entrenar modelos.</li>
    <li>✅ Documentar el estado inicial de la data (para auditoría y trazabilidad).</li>
    <li>✅ Crear features valiosas que mejoren el desempeño del modelo.</li>
</ul>
<p>En el próximo módulo, con datos limpios y enriquecidos, seleccionaremos algoritmos y entrenaremos nuestro primer modelo de Machine Learning.</p>
