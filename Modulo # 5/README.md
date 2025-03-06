<h1>Módulo 5: Evaluación y Optimización de Modelos</h1>

<h2>Objetivo</h2>
<p>Aprenderás a medir la calidad de tus modelos y aplicarás técnicas de optimización para mejorar su precisión y robustez.</p>

<hr>

<h2>Métricas Clave</h2>
<p>Las métricas dependen del tipo de problema:</p>
<ul>
    <li>Clasificación → Accuracy, Precision, Recall, F1 Score, ROC-AUC.</li>
    <li>Regresión → RMSE, MAE, R².</li>
</ul>

<pre><code>
from sklearn.metrics import classification_report
print(classification_report(y_test, y_pred))
</code></pre>

<hr>

<h2>Optimización de Hiperparámetros</h2>
<p>Usamos SageMaker Hyperparameter Tuning Jobs para probar diferentes combinaciones automáticamente.</p>

<pre><code>
from sagemaker.tuner import HyperparameterTuner
tuner = HyperparameterTuner(xgb, 'validation:auc', hyperparameter_ranges)
tuner.fit({'train': train_data_path})
</code></pre>

<hr>

<h2>Práctica: Evaluación y Tuning</h2>
<ul>
    <li>✅ Calcular métricas de evaluación.</li>
    <li>✅ Crear Tuning Job en SageMaker.</li>
    <li>✅ Comparar modelo inicial vs modelo optimizado.</li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>Un modelo bien optimizado mejora sustancialmente los resultados. En el próximo módulo veremos cómo ponerlo en producción.</p>
