<h1>Módulo 5: Evaluación y Optimización de Modelos</h1>

<h2>Objetivo</h2>
<p>En este módulo aprenderás a medir el desempeño real de un modelo entrenado, interpretar correctamente sus métricas y aplicar técnicas de optimización 
para ajustar sus hiperparámetros y mejorar su precisión y robustez. Un buen modelo no es solo el que "aprende", sino el que <strong>generaliza bien</strong> a nuevos datos.</p>

<hr>

<h2>¿Por qué es clave evaluar correctamente?</h2>
<p>Un modelo puede funcionar muy bien sobre los datos de entrenamiento, pero eso no garantiza que funcione bien sobre datos nuevos (datos reales en producción). 
De ahí la importancia de evaluar con un conjunto de prueba o validación que el modelo nunca vio durante el entrenamiento.</p>

<p><strong>Evaluar correctamente evita:</strong></p>
<ul>
    <li>✅ Sobreajuste (overfitting): el modelo memoriza en vez de aprender patrones generales.</li>
    <li>✅ Subajuste (underfitting): el modelo es demasiado simple y no captura la complejidad real.</li>
    <li>✅ Métricas engañosas: usar la métrica equivocada puede hacerte pensar que el modelo es bueno cuando no lo es.</li>
</ul>

<hr>

<h2>Métricas clave por tipo de problema</h2>
<p>Cada tipo de problema tiene métricas específicas:</p>

<h3>📂 Clasificación (predecir categorías)</h3>
<ul>
    <li><strong>Accuracy:</strong> porcentaje total de predicciones correctas.</li>
    <li><strong>Precision:</strong> de las predicciones positivas, ¿cuántas eran realmente positivas?</li>
    <li><strong>Recall (Sensibilidad):</strong> de los casos positivos reales, ¿cuántos detectó el modelo?</li>
    <li><strong>F1 Score:</strong> balance entre precisión y recall.</li>
    <li><strong>ROC-AUC:</strong> mide qué tan bien el modelo separa las clases.</li>
</ul>

<pre><code>
from sklearn.metrics import classification_report, roc_auc_score

print(classification_report(y_test, y_pred))
print(f'ROC-AUC: {roc_auc_score(y_test, y_prob)}')
</code></pre>

<h3>📊 Regresión (predecir valores numéricos)</h3>
<ul>
    <li><strong>RMSE (Root Mean Squared Error):</strong> error promedio cuadrático (da más peso a errores grandes).</li>
    <li><strong>MAE (Mean Absolute Error):</strong> error promedio absoluto (más interpretativo).</li>
    <li><strong>R² (Coeficiente de determinación):</strong> porcentaje de la varianza explicada por el modelo.</li>
</ul>

<pre><code>
from sklearn.metrics import mean_squared_error, mean_absolute_error, r2_score

print(f'RMSE: {mean_squared_error(y_test, y_pred, squared=False)}')
print(f'MAE: {mean_absolute_error(y_test, y_pred)}')
print(f'R²: {r2_score(y_test, y_pred)}')
</code></pre>

<hr>

<h2>¿Qué es la optimización de hiperparámetros?</h2>
<p>Entrenar un modelo implica ajustar sus <strong>parámetros internos</strong> (por ejemplo, coeficientes de una regresión). 
Pero cada algoritmo también tiene <strong>hiperparámetros</strong> externos, como:</p>
<ul>
    <li>✅ Profundidad de un árbol.</li>
    <li>✅ Tasa de aprendizaje.</li>
    <li>✅ Número de árboles en un Random Forest.</li>
</ul>

<p>Elegir buenos hiperparámetros puede marcar la diferencia entre un modelo mediocre y un modelo de clase mundial.</p>

<hr>

<h2>Enfoques para optimización de hiperparámetros</h2>
<h3>1️⃣ Búsqueda Manual (Grid Search)</h3>
<p>Definimos combinaciones fijas y entrenamos el modelo con cada una. Es simple, pero puede ser lento y costoso.</p>

<h3>2️⃣ Búsqueda Aleatoria (Random Search)</h3>
<p>Probamos combinaciones al azar dentro de un rango. Es más eficiente que grid search, pero no garantiza encontrar la mejor combinación.</p>

<h3>3️⃣ Optimización Bayesiana (SageMaker Automatic Tuning)</h3>
<p>Usa un enfoque probabilístico que aprende qué combinaciones funcionan mejor y explora de forma inteligente.</p>

<hr>

<h2>Optimización automática en SageMaker</h2>
<p>En AWS SageMaker, puedes crear un <strong>Hyperparameter Tuning Job</strong> que entrena automáticamente múltiples modelos, 
probando diferentes combinaciones de hiperparámetros y eligiendo la mejor.</p>

<h3>Ejemplo en código:</h3>
<pre><code>
from sagemaker.tuner import HyperparameterTuner, ContinuousParameter, IntegerParameter

# Rango de hiperparámetros
hyperparameter_ranges = {
    'eta': ContinuousParameter(0.01, 0.3),
    'max_depth': IntegerParameter(3, 10),
    'subsample': ContinuousParameter(0.5, 1.0)
}

# Tuning Job
tuner = HyperparameterTuner(
    estimator=xgb_estimator,
    objective_metric_name='validation:auc',
    hyperparameter_ranges=hyperparameter_ranges,
    max_jobs=10,
    max_parallel_jobs=2
)

# Ejecutar tuning
tuner.fit({'train': train_path, 'validation': validation_path})
</code></pre>

<p>Este proceso es <strong>serverless</strong>, lo cual significa que SageMaker provisiona automáticamente las instancias necesarias 
y te cobra solo por el tiempo de ejecución.</p>

<hr>

<h2>Comparar modelo inicial vs modelo optimizado</h2>
<p>Al final, comparas el desempeño del modelo original (sin tuning) vs el modelo final optimizado. 
Idealmente, deberías ver:</p>
<ul>
    <li>✅ Mejor precisión o menor error.</li>
    <li>✅ Mejor estabilidad (menor varianza en resultados al probar con nuevos datos).</li>
    <li>✅ Menor tiempo de inferencia (si optimizaste hiperparámetros de eficiencia).</li>
</ul>

<pre><code>
# Comparar métricas
print(f'Métricas iniciales: {base_metrics}')
print(f'Métricas optimizadas: {tuned_metrics}')
</code></pre>

<hr>

<h2>Práctica recomendada</h2>
<ol>
    <li>✅ Entrenar un modelo base sin optimización.</li>
    <li>✅ Evaluarlo usando métricas apropiadas.</li>
    <li>✅ Ejecutar un Hyperparameter Tuning Job en SageMaker.</li>
    <li>✅ Comparar desempeño antes y después del tuning.</li>
    <li>✅ Documentar el impacto de cada hiperparámetro.</li>
</ol>

<hr>

<h2>Enlaces útiles</h2>
<ul>
    <li><a href="https://scikit-learn.org/stable/modules/classes.html#module-sklearn.metrics" target="_blank">Métricas en scikit-learn</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning.html" target="_blank">Tuning Automático en SageMaker</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost-tuning.html" target="_blank">Ejemplo de Tuning con XGBoost</a></li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>Un modelo bien optimizado puede superar ampliamente un modelo entrenado sin tuning. 
Además, evaluar correctamente te permite detectar problemas como bias, sobreajuste o datos desbalanceados. 
En el próximo módulo, llevaremos nuestro modelo optimizado a producción.</p>
