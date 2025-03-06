<h1>Módulo 4: Creando Modelos de Machine Learning en AWS</h1>

<h2>Objetivo</h2>
<p>En este módulo aprenderás cómo seleccionar el algoritmo adecuado según el tipo de problema, 
configurarás un entorno de trabajo en SageMaker y crearás tu primer modelo de Machine Learning entrenado directamente en la nube.</p>

<hr>

<h2>Guía Completa de Selección de Algoritmos</h2>

<p>Elegir el algoritmo adecuado es uno de los pasos más importantes en cualquier proyecto de Machine Learning. 
Cada algoritmo tiene sus fortalezas, debilidades y casos ideales de uso. A continuación, exploramos los más importantes, 
clasificados por el tipo de problema que resuelven.</p>

<hr>

<h3>📂 Clasificación</h3>
<p>En problemas de clasificación, el objetivo es predecir una <strong>categoría</strong> o clase. Ejemplos:</p>
<ul>
    <li>Detectar si un correo es spam o no (clase binaria).</li>
    <li>Predecir el segmento de un cliente (clase múltiple).</li>
</ul>

<table border="1">
<tr>
    <th>Algoritmo</th>
    <th>Cómo funciona</th>
    <th>Ventajas</th>
    <th>Limitaciones</th>
    <th>Casos ideales</th>
</tr>
<tr>
    <td>Regresión Logística</td>
    <td>Modelo lineal que asigna probabilidades.</td>
    <td>Fácil de interpretar.</td>
    <td>No captura relaciones complejas.</td>
    <td>Problemas binarios simples.</td>
</tr>
<tr>
    <td>Random Forest</td>
    <td>Combina múltiples árboles de decisión.</td>
    <td>Robusto y tolerante al ruido.</td>
    <td>Poco interpretable.</td>
    <td>Datos estructurados con muchas variables.</td>
</tr>
<tr>
    <td>XGBoost</td>
    <td>Optimiza árboles usando boosting.</td>
    <td>Muy preciso, estándar en competencias.</td>
    <td>Puede sobreajustar.</td>
    <td>Cuando necesitas máxima precisión.</td>
</tr>
<tr>
    <td>Support Vector Machines (SVM)</td>
    <td>Encuentra un hiperplano óptimo para separar clases.</td>
    <td>Bueno en espacios complejos.</td>
    <td>Lento en datasets grandes.</td>
    <td>Pocos datos, alta dimensionalidad.</td>
</tr>
<tr>
    <td>Redes Neuronales</td>
    <td>Capa tras capa, aprende relaciones complejas.</td>
    <td>Flexible y potente.</td>
    <td>Requiere muchos datos y ajuste fino.</td>
    <td>Imágenes, texto o audio.</td>
</tr>
<tr>
    <td>Naive Bayes</td>
    <td>Calcula probabilidad basada en teorema de Bayes.</td>
    <td>Rápido y eficiente.</td>
    <td>Asume independencia entre variables.</td>
    <td>Clasificación de textos (spam).</td>
</tr>
</table>

<hr>

<h3>📊 Regresión</h3>
<p>En problemas de regresión, el objetivo es predecir un <strong>valor numérico</strong>. Ejemplos:</p>
<ul>
    <li>Predecir el precio de una casa.</li>
    <li>Predecir la demanda mensual de un producto.</li>
</ul>

<table border="1">
<tr>
    <th>Algoritmo</th>
    <th>Cómo funciona</th>
    <th>Ventajas</th>
    <th>Limitaciones</th>
    <th>Casos ideales</th>
</tr>
<tr>
    <td>Regresión Lineal</td>
    <td>Ajusta una línea que minimiza el error.</td>
    <td>Simple e interpretable.</td>
    <td>No captura relaciones complejas.</td>
    <td>Relaciones lineales claras.</td>
</tr>
<tr>
    <td>XGBoost</td>
    <td>Optimiza árboles usando boosting.</td>
    <td>Maneja relaciones complejas.</td>
    <td>Requiere ajuste fino.</td>
    <td>Datos tabulares con muchas columnas.</td>
</tr>
<tr>
    <td>Random Forest Regressor</td>
    <td>Promedia múltiples árboles de decisión.</td>
    <td>Robusto a outliers.</td>
    <td>Lento si hay muchos datos.</td>
    <td>Datos estructurados.</td>
</tr>
<tr>
    <td>Support Vector Regression (SVR)</td>
    <td>Encuentra un margen óptimo.</td>
    <td>Bueno para pocas variables.</td>
    <td>Poco eficiente con datos grandes.</td>
    <td>Pequeños datasets.</td>
</tr>
<tr>
    <td>Redes Neuronales</td>
    <td>Aprende patrones no lineales.</td>
    <td>Muy flexible.</td>
    <td>Requiere mucho dato y tuning.</td>
    <td>Series temporales, imágenes, etc.</td>
</tr>
</table>

<hr>

<h3>🔗 Clustering</h3>
<p>En problemas de clustering, el objetivo es <strong>descubrir grupos</strong> dentro de los datos. Ejemplos:</p>
<ul>
    <li>Segmentar clientes en grupos de comportamiento similar.</li>
    <li>Agrupar productos similares.</li>
</ul>

<table border="1">
<tr>
    <th>Algoritmo</th>
    <th>Cómo funciona</th>
    <th>Ventajas</th>
    <th>Limitaciones</th>
    <th>Casos ideales</th>
</tr>
<tr>
    <td>K-Means</td>
    <td>Asigna puntos al cluster más cercano.</td>
    <td>Simple y eficiente.</td>
    <td>Clusters esféricos, sensible a outliers.</td>
    <td>Segmentación clásica.</td>
</tr>
<tr>
    <td>DBSCAN</td>
    <td>Detecta grupos densos.</td>
    <td>No requiere número fijo de clusters.</td>
    <td>Difícil ajustar parámetros.</td>
    <td>Clusters irregulares.</td>
</tr>
<tr>
    <td>Hierarchical Clustering</td>
    <td>Crea una jerarquía de clusters.</td>
    <td>No requiere clusters fijos.</td>
    <td>Poco eficiente para datos grandes.</td>
    <td>Cuando queremos dendrogramas.</td>
</tr>
<tr>
    <td>Gaussian Mixture Models (GMM)</td>
    <td>Modela datos como mezcla de gaussianas.</td>
    <td>Flexible, clusters elípticos.</td>
    <td>Puede sobreajustar.</td>
    <td>Datos continuos con subgrupos.</td>
</tr>
</table>

<hr>

<h2>Factores a considerar al elegir algoritmo</h2>
<p>Además de entender qué hace cada algoritmo, es clave considerar:</p>
<ul>
    <li>📊 Cantidad de datos disponibles (algunos requieren más datos que otros).</li>
    <li>⚙️ Complejidad del problema (relaciones lineales o no lineales).</li>
    <li>🚀 Velocidad requerida (modelos en producción suelen necesitar predicciones rápidas).</li>
    <li>🧰 Facilidad de interpretación (¿necesitas explicarle el modelo a un gerente?).</li>
    <li>💸 Costos computacionales (redes neuronales consumen más recursos que regresiones lineales).</li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>No existe el <strong>mejor algoritmo universal</strong>. La clave es entender:</p>
<ul>
    <li>✅ Qué tipo de problema tienes.</li>
    <li>✅ Qué características tienen tus datos.</li>
    <li>✅ Qué necesitas priorizar (velocidad, precisión, interpretabilidad).</li>
</ul>
<p>Elegir el algoritmo correcto es un arte que se perfecciona con experiencia y pruebas. En SageMaker, tienes acceso a la mayoría de estos algoritmos preconstruidos, 
listos para entrenar directamente desde un notebook.</p>

<hr>

<h2>¿Qué es Amazon SageMaker?</h2>
<p><strong>Amazon SageMaker</strong> es la plataforma gestionada de AWS para el ciclo completo de Machine Learning. 
Te permite entrenar, optimizar, desplegar y monitorear modelos, todo desde un entorno unificado.</p>

<h3>Ventajas de entrenar en SageMaker</h3>
<ul>
    <li>🚀 Sin preocuparte por la infraestructura.</li>
    <li>🔧 Soporta algoritmos preconstruidos optimizados para AWS.</li>
    <li>📦 Permite traer tus propios algoritmos o frameworks (TensorFlow, PyTorch, Scikit-Learn).</li>
    <li>💰 Pago por uso: solo pagas mientras el modelo entrena.</li>
</ul>

<hr>

<h2>Flujo típico de entrenamiento en SageMaker</h2>
<p>Entrenar un modelo en SageMaker sigue este flujo:</p>
<ol>
    <li>📂 Subir datos preparados a S3 (ya limpios y listos desde el módulo 3).</li>
    <li>📒 Crear un Notebook en SageMaker Studio (entorno Jupyter gestionado).</li>
    <li>⚙️ Seleccionar algoritmo y configurar hiperparámetros.</li>
    <li>📊 Entrenar el modelo.</li>
    <li>💾 Guardar el modelo entrenado en S3 para futuras predicciones o despliegue.</li>
</ol>

<hr>

<h2>Entrenamiento con un algoritmo preconstruido</h2>
<p>Para esta práctica usaremos <strong>XGBoost</strong>, uno de los algoritmos más populares en Machine Learning.</p>
<h3>Ejemplo de código base</h3>
<pre><code>
from sagemaker import session, estimator
from sagemaker import XGBoost

# Configurar ubicación de datos y rol
s3_input_train = 's3://ml-curso-datos-limpiados/train.csv'
s3_output = 's3://ml-curso-modelos/xgboost/'

role = 'arn:aws:iam::123456789012:role/SageMakerRole'

# Crear Estimador
xgb_estimator = XGBoost(
    entry_point='train.py',
    framework_version='1.5-1',
    role=role,
    instance_count=1,
    instance_type='ml.m5.large',
    output_path=s3_output,
    hyperparameters={
        'objective': 'binary:logistic',
        'num_round': 100
    }
)

# Lanzar entrenamiento
xgb_estimator.fit({'train': s3_input_train})
</code></pre>

<hr>

<h2>Explicación paso a paso</h2>
<ul>
    <li>📂 <strong>Datos en S3:</strong> SageMaker no almacena datos directamente; usa S3 como fuente y destino.</li>
    <li>📒 <strong>Notebook de SageMaker:</strong> Puedes escribir código y ejecutar el entrenamiento desde la consola.</li>
    <li>🔧 <strong>Algoritmo preconstruido:</strong> XGBoost ya viene optimizado para SageMaker, solo defines hiperparámetros.</li>
    <li>🚀 <strong>Entrenamiento gestionado:</strong> AWS provisiona automáticamente la instancia necesaria.</li>
    <li>💾 <strong>Modelo guardado:</strong> El artefacto final (modelo) se guarda automáticamente en S3.</li>
</ul>

<hr>

<h2>Conceptos clave de entrenamiento</h2>
<ul>
    <li>🎯 <strong>Hiperparámetros:</strong> Son configuraciones del algoritmo, como la tasa de aprendizaje o el número de árboles.</li>
    <li>📊 <strong>Partición de datos:</strong> Normalmente se dividen en entrenamiento, validación y prueba.</li>
    <li>⏳ <strong>Batch vs Streaming:</strong> En este caso, entrenamos en batch, cargando todos los datos de golpe.</li>
    <li>🏗️ <strong>Artefactos:</strong> El modelo final se guarda como un archivo serializado (por ejemplo, model.tar.gz).</li>
</ul>

<hr>

<h2>Práctica: Tu primer modelo real en AWS</h2>
<p>En esta práctica, realizarás un flujo completo:</p>
<ol>
    <li>✅ Subir datos procesados a S3.</li>
    <li>✅ Crear un Notebook en SageMaker Studio.</li>
    <li>✅ Configurar y entrenar un modelo de clasificación con XGBoost.</li>
    <li>✅ Revisar métricas básicas durante el entrenamiento.</li>
    <li>✅ Guardar el modelo entrenado en S3.</li>
</ol>

<hr>

<h2>Enlaces útiles</h2>
<ul>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html" target="_blank">Introducción a Amazon SageMaker</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost.html" target="_blank">Guía de XGBoost en SageMaker</a></li>
    <li><a href="https://github.com/awslabs/amazon-sagemaker-examples" target="_blank">Ejemplos oficiales de SageMaker</a></li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>Con esto, completaste tu primer ciclo de entrenamiento de un modelo real en AWS. 
Ya viste cómo elegir un algoritmo, cargar datos, lanzar el entrenamiento y guardar el modelo. 
En el próximo módulo, aprenderás cómo evaluar el desempeño del modelo y ajustar sus hiperparámetros para lograr mejores resultados.</p>
