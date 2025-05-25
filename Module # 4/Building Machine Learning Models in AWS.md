<h1>Module 4: Building Machine Learning Models in AWS</h1>

<h2>Objective</h2>
<p>In this module, you’ll learn how to select the right algorithm based on your problem type, set up a working environment in SageMaker, and build your first Machine Learning model trained directly in the cloud.</p>

<hr>

<h2>Comprehensive Algorithm Selection Guide</h2>
<p>Choosing the right algorithm is one of the most important steps in any Machine Learning project. Each algorithm has its strengths, weaknesses, and ideal use cases. Below, we explore the most important ones, grouped by problem type.</p>

<hr>

<h3>📂 Classification</h3>
<p>In classification problems, the goal is to predict a <strong>category</strong> or class. Examples:</p>
<ul>
    <li>Detect whether an email is spam (binary class).</li>
    <li>Predict customer segments (multi-class).</li>
</ul>

<table border="1">
<tr>
    <th>Algorithm</th>
    <th>How it works</th>
    <th>Advantages</th>
    <th>Limitations</th>
    <th>Best for</th>
</tr>
<tr>
    <td>Logistic Regression</td>
    <td>Linear model that assigns probabilities.</td>
    <td>Easy to interpret.</td>
    <td>Doesn’t capture complex relationships.</td>
    <td>Simple binary problems.</td>
</tr>
<tr>
    <td>Random Forest</td>
    <td>Combines multiple decision trees.</td>
    <td>Robust and noise-tolerant.</td>
    <td>Less interpretable.</td>
    <td>Structured data with many variables.</td>
</tr>
<tr>
    <td>XGBoost</td>
    <td>Boosts tree performance iteratively.</td>
    <td>Highly accurate, widely used in competitions.</td>
    <td>Can overfit if not tuned well.</td>
    <td>When maximum accuracy is needed.</td>
</tr>
<tr>
    <td>Support Vector Machines (SVM)</td>
    <td>Finds the optimal hyperplane to separate classes.</td>
    <td>Great for complex spaces.</td>
    <td>Slow with large datasets.</td>
    <td>High-dimensional, small datasets.</td>
</tr>
<tr>
    <td>Neural Networks</td>
    <td>Layered models that learn complex patterns.</td>
    <td>Powerful and flexible.</td>
    <td>Requires a lot of data and fine-tuning.</td>
    <td>Images, text, audio.</td>
</tr>
<tr>
    <td>Naive Bayes</td>
    <td>Uses Bayes' Theorem for probability-based classification.</td>
    <td>Fast and efficient.</td>
    <td>Assumes variable independence.</td>
    <td>Text classification (e.g., spam detection).</td>
</tr>
</table>

<hr>

<h3>📊 Regression</h3>
<p>In regression problems, the goal is to predict a <strong>numeric value</strong>. Examples:</p>
<ul>
    <li>Predicting house prices.</li>
    <li>Forecasting monthly product demand.</li>
</ul>

<table border="1">
<tr>
    <th>Algorithm</th>
    <th>How it works</th>
    <th>Advantages</th>
    <th>Limitations</th>
    <th>Best for</th>
</tr>
<tr>
    <td>Linear Regression</td>
    <td>Fits a line that minimizes error.</td>
    <td>Simple and interpretable.</td>
    <td>Doesn’t capture non-linear relationships.</td>
    <td>Clear linear trends.</td>
</tr>
<tr>
    <td>XGBoost</td>
    <td>Boosts tree performance iteratively.</td>
    <td>Handles complex relationships.</td>
    <td>Requires parameter tuning.</td>
    <td>Tabular data with many features.</td>
</tr>
<tr>
    <td>Random Forest Regressor</td>
    <td>Averages multiple decision trees.</td>
    <td>Robust to outliers.</td>
    <td>Slower with large datasets.</td>
    <td>Structured data.</td>
</tr>
<tr>
    <td>Support Vector Regression (SVR)</td>
    <td>Finds an optimal margin.</td>
    <td>Great with few variables.</td>
    <td>Not efficient with large data.</td>
    <td>Small datasets.</td>
</tr>
<tr>
    <td>Neural Networks</td>
    <td>Learn non-linear patterns.</td>
    <td>Highly flexible.</td>
    <td>Needs large data and tuning.</td>
    <td>Time series, images, etc.</td>
</tr>
</table>

<hr>

<h3>🔗 Clustering</h3>
<p>In clustering problems, the goal is to <strong>discover groups</strong> within your data. Examples:</p>
<ul>
    <li>Segmenting customers based on behavior.</li>
    <li>Grouping similar products.</li>
</ul>

<table border="1">
<tr>
    <th>Algorithm</th>
    <th>How it works</th>
    <th>Advantages</th>
    <th>Limitations</th>
    <th>Best for</th>
</tr>
<tr>
    <td>K-Means</td>
    <td>Assigns points to the nearest cluster.</td>
    <td>Simple and efficient.</td>
    <td>Assumes spherical clusters, sensitive to outliers.</td>
    <td>Standard segmentation.</td>
</tr>
<tr>
    <td>DBSCAN</td>
    <td>Finds dense groups of data.</td>
    <td>No need to predefine cluster count.</td>
    <td>Hard to tune parameters.</td>
    <td>Irregular clusters.</td>
</tr>
<tr>
    <td>Hierarchical Clustering</td>
    <td>Builds a tree of clusters (dendrogram).</td>
    <td>No fixed number of clusters needed.</td>
    <td>Not scalable for large data.</td>
    <td>When visual hierarchy is important.</td>
</tr>
<tr>
    <td>Gaussian Mixture Models (GMM)</td>
    <td>Models data as a mix of Gaussians.</td>
    <td>Flexible, elliptical clusters.</td>
    <td>Can overfit.</td>
    <td>Continuous data with subgroups.</td>
</tr>
</table>

<hr>

<h2>Key Factors When Choosing an Algorithm</h2>
<ul>
    <li>📊 Amount of data (some models need more than others)</li>
    <li>⚙️ Problem complexity (linear vs. non-linear relationships)</li>
    <li>🚀 Required speed (production models need fast predictions)</li>
    <li>🧰 Interpretability (can you explain it to a manager?)</li>
    <li>💸 Computational cost (neural networks are resource-intensive)</li>
</ul>

<hr>

<h2>Conclusion</h2>
<p>There’s no such thing as the <strong>best universal algorithm</strong>. The key is to understand:</p>
<ul>
    <li>✅ The type of problem you’re solving</li>
    <li>✅ Your data’s characteristics</li>
    <li>✅ Your priorities (speed, accuracy, interpretability)</li>
</ul>
<p>Choosing the right algorithm is a skill that improves with experience and experimentation. In SageMaker, most of these algorithms are prebuilt and ready to use from a notebook.</p>

<hr>

<h2>What Is Amazon SageMaker?</h2>
<p><strong>Amazon SageMaker</strong> is AWS’s managed platform for the full Machine Learning lifecycle. You can train, optimize, deploy, and monitor models in a single integrated environment.</p>

<h3>Why Train Models in SageMaker?</h3>
<ul>
    <li>🚀 No infrastructure management needed</li>
    <li>🔧 Optimized prebuilt algorithms available</li>
    <li>📦 Bring your own code or framework (TensorFlow, PyTorch, Scikit-learn)</li>
    <li>💰 Pay as you go—you only pay while training runs</li>
</ul>

<hr>

<h2>Typical SageMaker Training Workflow</h2>
<ol>
    <li>📂 Upload cleaned data to S3 (from Module 3)</li>
    <li>📒 Create a notebook in SageMaker Studio (Jupyter-based)</li>
    <li>⚙️ Choose algorithm and configure hyperparameters</li>
    <li>📊 Train the model</li>
    <li>💾 Save the trained model to S3</li>
</ol>

<hr>

<h2>Training with a Prebuilt Algorithm</h2>
<p>We’ll use <strong>XGBoost</strong>, one of the most popular ML algorithms.</p>

<h3>Sample Code</h3>
<pre><code>
from sagemaker import session, estimator
from sagemaker import XGBoost

s3_input_train = 's3://ml-course-data-cleaned/train.csv'
s3_output = 's3://ml-course-models/xgboost/'
role = 'arn:aws:iam::123456789012:role/SageMakerRole'

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

xgb_estimator.fit({'train': s3_input_train})
</code></pre>

<hr>

<h2>Step-by-Step Explanation</h2>
<ul>
    <li>📂 <strong>Data in S3:</strong> SageMaker uses S3 as the input/output source.</li>
    <li>📒 <strong>Notebook:</strong> You code and launch training from SageMaker Studio.</li>
    <li>🔧 <strong>Prebuilt algorithm:</strong> XGBoost is already optimized—just define the parameters.</li>
    <li>🚀 <strong>Managed training:</strong> AWS provisions the necessary infrastructure.</li>
    <li>💾 <strong>Saved model:</strong> The final model artifact is saved to S3.</li>
</ul>

<hr>

<h2>Core Training Concepts</h2>
<ul>
    <li>🎯 <strong>Hyperparameters:</strong> Settings like learning rate and number of trees</li>
    <li>📊 <strong>Data splits:</strong> Usually split into train, validation, and test sets</li>
    <li>⏳ <strong>Batch vs Streaming:</strong> Here we use batch (full data load)</li>
    <li>🏗️ <strong>Artifacts:</strong> Final model saved as a file (e.g., model.tar.gz)</li>
</ul>

<hr>

<h2>Hands-On: Your First Real Model in AWS</h2>
<ol>
    <li>✅ Upload processed data to S3</li>
    <li>✅ Create a notebook in SageMaker Studio</li>
    <li>✅ Configure and train a classifier with XGBoost</li>
    <li>✅ Review training metrics</li>
    <li>✅ Save the model to S3</li>
</ol>

<hr>

<h2>Helpful Links</h2>
<ul>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html" target="_blank">Amazon SageMaker Overview</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/xgboost.html" target="_blank">XGBoost in SageMaker</a></li>
    <li><a href="https://github.com/awslabs/amazon-sagemaker-examples" target="_blank">Official SageMaker Examples</a></li>
</ul>

<hr>

<h2>Conclusion</h2>
<p>You've now completed your first full model training cycle in AWS. You’ve seen how to select the right algorithm, upload data, run training, and store the model. In the next module, we’ll learn how to evaluate your model’s performance and fine-tune it for better results.</p>
