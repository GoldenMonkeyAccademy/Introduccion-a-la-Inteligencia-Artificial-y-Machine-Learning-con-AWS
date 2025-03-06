<h1>Módulo 4: Creando Modelos de Machine Learning en AWS</h1>

<h2>Objetivo</h2>
<p>Aprenderás a seleccionar algoritmos adecuados según el tipo de problema, crearás tu primer modelo de Machine Learning usando SageMaker y entenderás las bases del entrenamiento en la nube.</p>

<hr>

<h2>Selección de Algoritmo</h2>
<p>La selección de algoritmo depende de varios factores:</p>
<ul>
    <li>¿Es problema de clasificación, regresión o clustering?</li>
    <li>¿Cuántos datos tienes?</li>
    <li>¿Qué tan interpretables necesitas que sean los resultados?</li>
</ul>
<p><strong>Guía rápida:</strong></p>
<ul>
    <li>Clasificación → Random Forest, XGBoost, Regresión Logística.</li>
    <li>Regresión → Regresión Lineal, XGBoost.</li>
    <li>Clustering → K-Means, DBSCAN.</li>
</ul>

<hr>

<h2>Entrenamiento en SageMaker</h2>
<p>SageMaker es el servicio estrella de AWS para Machine Learning. En este módulo:</p>
<ol>
    <li>Subirás tus datos a S3.</li>
    <li>Configurarás un notebook en SageMaker Studio.</li>
    <li>Crearás un modelo usando un algoritmo preconstruido.</li>
    <li>Entrenarás y guardarás el modelo.</li>
</ol>

<p><strong>Código base:</strong></p>
<pre><code>
from sagemaker import XGBoost
xgb = XGBoost(role=role, instance_type='ml.m5.large', output_path=output_path)
xgb.fit({'train': train_data_path})
</code></pre>

<hr>

<h2>Práctica: Tu primer modelo en SageMaker</h2>
<ul>
    <li>✅ Cargar datos en S3.</li>
    <li>✅ Crear notebook en SageMaker Studio.</li>
    <li>✅ Entrenar modelo de clasificación usando XGBoost.</li>
    <li>✅ Guardar el modelo entrenado en S3.</li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>Ya tienes tu primer modelo entrenado en AWS. En el próximo módulo aprenderás a optimizar su desempeño.</p>
