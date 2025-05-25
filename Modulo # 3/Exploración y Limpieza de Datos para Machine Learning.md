<h1>Module 3: Exploring and Cleaning Data for Machine Learning</h1>

<h2>Objective</h2>
<p>In this module, you’ll learn how to explore, understand, and clean data using AWS tools and Python. This step is crucial for any Machine Learning project, as the quality of your data directly impacts your model’s performance.</p>

<hr>

<h2>What Is Data Exploration?</h2>
<p>Data exploration means understanding what the data looks like, what information it contains, spotting errors or outliers, and uncovering early patterns. Without good exploratory analysis, any model you train will be a black box with no context.</p>

<h3>Why Is Exploration So Important?</h3>
<ul>
  <li>✅ Detect missing, duplicated, or inconsistent data</li>
  <li>✅ Understand distributions, biases, and outliers</li>
  <li>✅ Identify correlations and variable relationships</li>
  <li>✅ Decide whether transformations or scaling are needed</li>
</ul>

<h3>Key Tools</h3>
<p>We’ll use the following for data exploration:</p>
<ul>
  <li>📊 Pandas (data manipulation)</li>
  <li>📈 Matplotlib and Seaborn (visualizations)</li>
  <li>🔎 Amazon Athena (SQL queries on S3)</li>
</ul>

<hr>

<h2>Types of Data</h2>
<p>Accurately identifying the data type is essential to choose the right cleaning and visualization strategies:</p>
<ul>
  <li><strong>Structured:</strong> Tabular data (CSV, Excel, SQL)</li>
  <li><strong>Semi-structured:</strong> JSON, XML, formatted logs</li>
  <li><strong>Unstructured:</strong> Images, audio, video, free-text</li>
  <li><strong>Time Series:</strong> Data with a time component, like daily sales</li>
</ul>

<hr>

<h2>Data Distributions</h2>
<p>Understanding the shape of each variable helps decide on transformations or special techniques:</p>
<ul>
  <li>📊 <strong>Normal Distribution:</strong> Classic bell curve</li>
  <li>📉 <strong>Skewed:</strong> Data concentrated on one end</li>
  <li>📈 <strong>Multimodal:</strong> Multiple peaks or clusters</li>
</ul>

<hr>

<h2>Time Series: Trends and Seasonality</h2>
<p>For data like sales, weather, or operational metrics, it’s important to identify:</p>
<ul>
  <li>📈 <strong>Trend:</strong> General upward or downward movement</li>
  <li>🔄 <strong>Seasonality:</strong> Repeating patterns (daily, monthly, etc.)</li>
</ul>

<hr>

<h2>First Step: Load Data into a Notebook</h2>
<p>To explore data, you must first load it. In AWS, you can do this in several ways:</p>
<ul>
  <li>📂 Read a CSV file directly from S3 using Pandas</li>
  <li>📊 Query data from Redshift or Athena</li>
  <li>🔗 Use SageMaker Data Wrangler for loading, transforming, and visualizing data</li>
</ul>

<pre><code>
import pandas as pd
import boto3
s3 = boto3.client('s3')
response = s3.get_object(Bucket='ml-course-data-cleaned', Key='sales_processed.csv')
df = pd.read_csv(response['Body'])
df.head()
</code></pre>

<hr>

<h2>Initial Check: Assess Data Quality</h2>
<p>Before starting any analysis or training, it’s essential to run an initial quality check on the dataset. Here's an example with the sales dataset and how to perform key checks using Pandas.</p>

<h3>📊 Sample Dataset (sales.csv)</h3>
<!-- Sample table omitted for brevity – assume included in final page -->

<h3>✔️ 1. Number of Records and Columns</h3>
<pre><code>
print(f'Records: {df.shape[0]}')
print(f'Columns: {df.shape[1]}')
</code></pre>

<h3>✔️ 2. Data Types</h3>
<pre><code>
print(df.dtypes)
</code></pre>

<h3>✔️ 3. Missing Values</h3>
<pre><code>
print(df.isnull().sum())
</code></pre>

<h3>✔️ 4. Duplicate Records</h3>
<pre><code>
print(f'Duplicates: {df.duplicated().sum()}')
</code></pre>

<h3>✔️ 5. Unnecessary Columns</h3>
<pre><code>
df = df.drop(columns=['payment_method'])  # If not relevant
</code></pre>

<h3>Final Summary Table</h3>
<!-- Summary table omitted for brevity – assume included in final page -->

<hr>

<pre><code>
df.info()
df.describe()
df.isnull().sum()
df.duplicated().sum()
</code></pre>

<hr>

<h2>📋 Best Practices When Exploring Data</h2>

<h3>✅ Initial Checkup</h3>
<p>Think of it as a "health check" for your data. This ensures completeness, consistency, and quality before training any model.</p>

<h3>✅ Common Unnecessary Columns</h3>
<ul>
  <li>📑 Internal notes or comments</li>
  <li>🔗 System process IDs with no modeling value</li>
  <li>👤 Record uploader (irrelevant to prediction)</li>
</ul>

<h3>✅ Special Check on Dates</h3>
<pre><code>
df['date'] = pd.to_datetime(df['date'], errors='coerce')
</code></pre>
<p>Also, graph records by date to spot gaps or outliers:</p>
<ul>
  <li>📉 Missing days</li>
  <li>⚠️ Years out of range (e.g., 1900 or 2100)</li>
</ul>

<h3>✅ Categorical Variable Cardinality</h3>
<pre><code>
df['product'].nunique()
</code></pre>
<p>Group large categories (e.g., thousands of product names → categories like “Electronics”, “Furniture”).</p>

<h3>✅ Document Issues Found</h3>
<p>Track all findings (nulls, duplicates, formatting issues) in a <code>data_quality_report.md</code>.</p>

<h3>✅ Automate the Initial Check</h3>
<p>Use a base notebook that loads data, runs quality checks, and outputs graphs and metrics.</p>

<h3>📊 Sample Workflow</h3>
<ul>
  <li>📂 Load data</li>
  <li>🔍 Initial check</li>
  <li>📊 Exploratory visualizations</li>
  <li>💧 Cleaning</li>
  <li>⚒️ Feature Engineering</li>
</ul>

<hr>

<h2>📚 Recommended Links</h2>
<ul>
  <li><a href="https://pandas.pydata.org/docs/" target="_blank">Pandas Documentation</a></li>
  <li><a href="https://matplotlib.org/stable/contents.html" target="_blank">Matplotlib Docs</a></li>
  <li><a href="https://seaborn.pydata.org/" target="_blank">Seaborn Docs</a></li>
</ul>

<hr>

<h2>Exploratory Visualizations</h2>
<ul>
  <li>📊 Histograms – value distributions</li>
  <li>📉 Boxplots – outlier detection</li>
  <li>📈 Scatter plots – variable relationships</li>
  <li>🔥 Heatmaps – numeric correlations</li>
</ul>

<pre><code>
import matplotlib.pyplot as plt
plt.hist(df['sales'], bins=20)
plt.title('Sales Distribution')
plt.show()
</code></pre>

<hr>

<h2>Common Errors to Spot</h2>
<ul>
  <li>⚠️ Dates out of range (year 1900 or 2100)</li>
  <li>⚠️ Negative values in price or age</li>
  <li>⚠️ Categorical columns with excessive cardinality</li>
  <li>⚠️ Duplicated rows</li>
</ul>

<pre><code>
df.duplicated().sum()
</code></pre>

<hr>

<h2>Transformation and Feature Engineering</h2>
<ul>
  <li>✅ Encode categories into numbers</li>
  <li>✅ Normalize (Min-Max) or standardize (Z-score)</li>
  <li>✅ Create new features (ratios, buckets)</li>
</ul>

<pre><code>
df['price_category'] = pd.qcut(df['price'], q=4, labels=['low', 'medium', 'high', 'very high'])
</code></pre>

<hr>

<h2>Hands-On Practice</h2>
<p>With the sales dataset in S3, do the following:</p>
<ol>
  <li>Load the data</li>
  <li>Check structure, types, and nulls</li>
  <li>Plot key distributions</li>
  <li>Clean duplicates and errors</li>
  <li>Create at least two new variables</li>
</ol>

<hr>

<h2>Conclusion</h2>
<p>Clean data is the foundation for accurate models. In the next module, we’ll train our first model.</p>
