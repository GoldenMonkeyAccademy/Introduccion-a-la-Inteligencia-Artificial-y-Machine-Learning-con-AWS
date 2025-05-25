<h1>Module 5: Model Evaluation and Optimization</h1>

<h2>Objective</h2>
<p>In this module, you’ll learn how to measure the real performance of a trained model, interpret its metrics correctly, and apply optimization techniques to tune hyperparameters for better accuracy and robustness. A good model isn’t just one that “learns,” but one that <strong>generalizes well</strong> to new data.</p>

<hr>

<h2>Why Proper Evaluation Matters</h2>
<p>A model might perform well on training data, but that doesn’t mean it will work well on unseen data (real-world production data). That’s why it’s essential to evaluate it using a test or validation set the model never saw during training.</p>

<p><strong>Proper evaluation helps avoid:</strong></p>
<ul>
    <li>✅ Overfitting: the model memorizes instead of learning general patterns.</li>
    <li>✅ Underfitting: the model is too simple and misses important complexity.</li>
    <li>✅ Misleading metrics: the wrong metric can make a model look better than it is.</li>
</ul>

<hr>

<h2>Key Metrics by Problem Type</h2>
<p>Different problem types require different metrics:</p>

<h3>📂 Classification (predicting categories)</h3>
<ul>
    <li><strong>Accuracy:</strong> overall percentage of correct predictions.</li>
    <li><strong>Precision:</strong> of all positive predictions, how many were actually positive?</li>
    <li><strong>Recall (Sensitivity):</strong> of all actual positives, how many were correctly predicted?</li>
    <li><strong>F1 Score:</strong> harmonic mean of precision and recall.</li>
    <li><strong>ROC-AUC:</strong> measures how well the model separates classes.</li>
</ul>

<pre><code>
from sklearn.metrics import classification_report, roc_auc_score

print(classification_report(y_test, y_pred))
print(f'ROC-AUC: {roc_auc_score(y_test, y_prob)}')
</code></pre>

<h3>📊 Regression (predicting numeric values)</h3>
<ul>
    <li><strong>RMSE (Root Mean Squared Error):</strong> penalizes larger errors more heavily.</li>
    <li><strong>MAE (Mean Absolute Error):</strong> average magnitude of errors (easier to interpret).</li>
    <li><strong>R² (R-squared):</strong> proportion of variance explained by the model.</li>
</ul>

<pre><code>
from sklearn.metrics import mean_squared_error, mean_absolute_error, r2_score

print(f'RMSE: {mean_squared_error(y_test, y_pred, squared=False)}')
print(f'MAE: {mean_absolute_error(y_test, y_pred)}')
print(f'R²: {r2_score(y_test, y_pred)}')
</code></pre>

<hr>

<h2>What Is Hyperparameter Optimization?</h2>
<p>Training a model means adjusting its <strong>internal parameters</strong> (like weights). But every algorithm also has <strong>external hyperparameters</strong> that influence training, such as:</p>
<ul>
    <li>✅ Tree depth.</li>
    <li>✅ Learning rate.</li>
    <li>✅ Number of trees in a Random Forest.</li>
</ul>

<p>Choosing good hyperparameters can be the difference between a mediocre model and a world-class one.</p>

<hr>

<h2>Hyperparameter Optimization Methods</h2>

<h3>1️⃣ Manual Search (Grid Search)</h3>
<p>You define a fixed set of combinations and train the model with each one. Simple, but time-consuming and computationally expensive.</p>

<h3>2️⃣ Random Search</h3>
<p>Tries random combinations within a range. More efficient than grid search, but no guarantee of best result.</p>

<h3>3️⃣ Bayesian Optimization (SageMaker Automatic Tuning)</h3>
<p>A probabilistic method that learns from previous trials to intelligently explore promising combinations.</p>

<hr>

<h2>Automatic Tuning in SageMaker</h2>
<p>In AWS SageMaker, you can launch a <strong>Hyperparameter Tuning Job</strong> that trains multiple models automatically with different hyperparameter combinations, selecting the best one.</p>

<h3>Sample Code:</h3>
<pre><code>
from sagemaker.tuner import HyperparameterTuner, ContinuousParameter, IntegerParameter

# Define search ranges
hyperparameter_ranges = {
    'eta': ContinuousParameter(0.01, 0.3),
    'max_depth': IntegerParameter(3, 10),
    'subsample': ContinuousParameter(0.5, 1.0)
}

# Tuner
tuner = HyperparameterTuner(
    estimator=xgb_estimator,
    objective_metric_name='validation:auc',
    hyperparameter_ranges=hyperparameter_ranges,
    max_jobs=10,
    max_parallel_jobs=2
)

# Launch tuning
tuner.fit({'train': train_path, 'validation': validation_path})
</code></pre>

<p>This process is <strong>serverless</strong>, meaning SageMaker provisions the resources automatically and charges only for actual usage time.</p>

<hr>

<h2>Comparing Baseline vs Optimized Models</h2>
<p>At the end, compare the baseline (non-tuned) model’s performance with the optimized one. Ideally, you should see:</p>
<ul>
    <li>✅ Better accuracy or lower error.</li>
    <li>✅ Improved consistency (lower variance with new data).</li>
    <li>✅ Faster inference (if you tuned for efficiency).</li>
</ul>

<pre><code>
# Compare metrics
print(f'Baseline metrics: {base_metrics}')
print(f'Tuned model metrics: {tuned_metrics}')
</code></pre>

<hr>

<h2>Recommended Practice</h2>
<ol>
    <li>✅ Train a baseline model without optimization.</li>
    <li>✅ Evaluate it using appropriate metrics.</li>
    <li>✅ Run a SageMaker Hyperparameter Tuning Job.</li>
    <li>✅ Compare performance before and after tuning.</li>
    <li>✅ Document the impact of each hyperparameter.</li>
</ol>

<hr>

<h2>Helpful Links</h2>
<ul>
    <li><a href="https://scikit-learn.org/stable/modules/classes.html#module-sklearn.metrics" target="_blank">Scikit-learn Metrics Reference</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning.html" target="_blank">Automatic Tuning in SageMaker</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost-tuning.html" target="_blank">XGBoost Tuning Example</a></li>
</ul>

<hr>

<h2>Conclusion</h2>
<p>A well-optimized model can significantly outperform one trained with default settings. Evaluating correctly helps uncover issues like bias, overfitting, or imbalanced data. In the next module, we’ll take our optimized model and deploy it to production.</p>
