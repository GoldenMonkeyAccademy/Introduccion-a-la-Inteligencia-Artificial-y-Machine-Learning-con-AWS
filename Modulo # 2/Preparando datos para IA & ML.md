<h1>Module 2: Preparing Data for AI/ML</h1>

<h2>Objective</h2>
<p>In this module, you'll learn why data is the heart of any Machine Learning project, how to evaluate the quality of a dataset, and what AWS offers to build efficient data repositories and pipelines. 
By the end, you'll create your first real data pipeline in AWS, combining storage, ingestion, and processing.</p>

<hr>

<section>
  <h2>What Makes a Good Dataset for AI/ML?</h2>
  <p>A model is only as good as the data it’s trained on. That’s why understanding what makes a dataset useful is <strong>critical</strong>. Below are the key characteristics of a good dataset, with practical examples:</p>

  <h3>✅ Quality</h3>
  <ul>
    <li><strong>Good example:</strong> Customer dataset with valid birthdates, no duplicates, and complete fields like name, email, and purchase history.</li>
    <li><strong>Bad example:</strong> Dates like “32/13/2022”, missing emails, or duplicated customers with slight name variations.</li>
  </ul>

  <h3>✅ Volume</h3>
  <ul>
    <li><strong>Good example:</strong> 50,000 e-commerce transactions to train a recommendation model.</li>
    <li><strong>Bad example:</strong> Only 80 records: the model can’t generalize and will overfit easily.</li>
  </ul>

  <h3>✅ Variety</h3>
  <ul>
    <li><strong>Good example:</strong> Combining sales, weather, and inventory data to forecast supermarket demand.</li>
    <li><strong>Bad example:</strong> Only using sales history without accounting for promotions or events.</li>
  </ul>

  <h3>✅ Representativeness</h3>
  <ul>
    <li><strong>Good example:</strong> Fraud data from various countries, currencies, and transaction types.</li>
    <li><strong>Bad example:</strong> Training only with data from one country and expecting global results.</li>
  </ul>

  <h3>✅ Freshness</h3>
  <ul>
    <li><strong>Good example:</strong> A recommendation system retrained daily with recent user interactions.</li>
    <li><strong>Bad example:</strong> Using data from three years ago to detect current fraud patterns.</li>
  </ul>

  <p><strong>💡 Remember:</strong> <em>Garbage In, Garbage Out.</em> No matter how advanced your algorithm is, poor data will always yield poor results.</p>
</section>

<hr>

<h2>Creating Data Repositories in AWS</h2>

<h3>What Is a Data Lake?</h3>
<p>A <strong>Data Lake</strong> is a central repository where <strong>all types of data</strong> are stored—regardless of format or structure. It can contain:</p>
<ul>
    <li>Structured data (CSV tables, relational database exports)</li>
    <li>Semi-structured data (JSON or XML files)</li>
    <li>Unstructured data (images, videos, logs)</li>
</ul>
<p>The idea is to store data as-is, without filtering or transforming it right away. This allows for exploration and processing later, depending on the use case.</p>

<hr>

<h2>Amazon S3: The Core of the Data Lake</h2>
<p><strong>Amazon S3</strong> is the core service for building Data Lakes on AWS. It stores raw data, processed data, trained models, and ML artifacts.</p>

<h3>Why is it Key for AI/ML?</h3>
<ul>
    <li>✅ Flexibility: supports many formats—CSV, JSON, Parquet, images, videos</li>
    <li>✅ Scalability: stores petabytes without worrying about limits</li>
    <li>✅ Integration: works with SageMaker, Glue, Athena, and more</li>
</ul>

<h3>Storage Classes</h3>
<table border="1" cellpadding="5" cellspacing="0">
    <thead>
        <tr>
            <th>Class</th>
            <th>Description</th>
            <th>Use Cases</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>S3 Standard</td>
            <td>High availability and durability</td>
            <td>Frequently accessed data</td>
        </tr>
        <tr>
            <td>S3 Intelligent-Tiering</td>
            <td>Automatically moves data between hot and cold tiers</td>
            <td>Unpredictable access patterns</td>
        </tr>
        <tr>
            <td>S3 Standard-IA</td>
            <td>Infrequent access data</td>
            <td>Recent or historical backups</td>
        </tr>
        <tr>
            <td>S3 Glacier Instant Retrieval</td>
            <td>Cold storage with fast access</td>
            <td>Old data, occasional queries</td>
        </tr>
        <tr>
            <td>S3 Glacier Deep Archive</td>
            <td>Lowest-cost storage</td>
            <td>Regulatory or long-term archives</td>
        </tr>
    </tbody>
</table>

<h3>Lifecycle Rules</h3>
<p>With <strong>Lifecycle Rules</strong>, S3 can automatically move objects between storage classes or delete them after a set time. Example:</p>
<ul>
    <li>🔄 Move raw data to Glacier after 90 days</li>
    <li>🗑️ Delete temporary files after 30 days</li>
</ul>

<h3>Security: Bucket Policies and Encryption</h3>
<p>Every bucket should have clear access rules. With <strong>Bucket Policies</strong>, you define:</p>
<ul>
    <li>Who can read or write</li>
    <li>Which services can access it (e.g., only SageMaker or Glue)</li>
    <li>Whether public access is allowed or denied</li>
</ul>

<p>S3 also supports automatic encryption:</p>
<ul>
    <li>SSE-S3 (server-side encryption managed by AWS)</li>
    <li>SSE-KMS (encryption with customer keys in AWS KMS)</li>
    <li>Client-side encryption (upload pre-encrypted files)</li>
</ul>

<h3>VPC Endpoints</h3>
<p>If your notebooks or pipelines run in a private VPC, use a <strong>VPC Endpoint</strong> to connect to S3 without using the public internet.</p>

<hr>

<h2>Other Key AWS Services for Data Engineering</h2>

<h3>Amazon Kinesis Data Streams</h3>
<p><strong>What is it?</strong></p>
<p>A real-time data ingestion service. It captures continuous data streams like logs, website clicks, IoT metrics, or financial events.</p>
<p><strong>Use Cases:</strong></p>
<ul>
    <li>Processing web server logs in real time</li>
    <li>Analyzing user behavior while browsing an app</li>
    <li>Capturing sensor data (e.g., temperature, humidity)</li>
</ul>
<p><strong>Why is it relevant to AI/ML?</strong></p>
<p>Real-time data can feed fraud detection models, recommendation systems, or predictive maintenance engines with fresh, actionable input.</p>

<hr>

<h3>Amazon Kinesis Data Firehose</h3>
<p><strong>What is it?</strong></p>
<p>A fully managed service that delivers streaming data directly to S3, Redshift, or OpenSearch—no extra code required.</p>
<p><strong>Use Cases:</strong></p>
<ul>
    <li>Capture logs and automatically store them in S3</li>
    <li>Stream raw data into a Data Lake</li>
    <li>Index logs into OpenSearch for security analytics</li>
</ul>
<p><strong>Why is it relevant to AI/ML?</strong></p>
<p>Enables no-code, serverless data pipelines that ensure data lands in S3 or Redshift ready for modeling.</p>

<hr>

<h3>Amazon Managed Service for Apache Flink</h3>
<p><strong>What is it?</strong></p>
<p>A managed service to run real-time data processing apps using Apache Flink.</p>
<p><strong>Use Cases:</strong></p>
<ul>
    <li>Calculate metrics or KPIs in real time</li>
    <li>Detect complex patterns (time series analysis)</li>
    <li>Enrich streams with historical data</li>
</ul>
<p><strong>Why is it relevant to AI/ML?</strong></p>
<p>When your models rely on streaming data (e.g., fraud detection, log analysis), Flink can transform and enrich the data before it reaches the model.</p>

<hr>

<h3>AWS Glue</h3>
<p><strong>What is it?</strong></p>
<p>A serverless ETL (Extract, Transform, Load) service for cleaning, transforming, and moving data between sources like S3, RDS, and Redshift.</p>
<p><strong>Use Cases:</strong></p>
<ul>
    <li>Convert raw data in S3 to optimized formats (like Parquet)</li>
    <li>Join data from multiple sources (e.g., app logs + sales)</li>
    <li>Clean data by removing duplicates or corrupted records</li>
</ul>
<p><strong>Why is it relevant to AI/ML?</strong></p>
<p>ML models are only as good as the data behind them. Glue ensures data is clean and ready for training.</p>

<hr>

<h3>Glue Data Catalog</h3>
<p><strong>What is it?</strong></p>
<p>A centralized catalog that stores schema and metadata for datasets in S3 and other sources—essentially a “library” that describes where data lives and how it’s structured.</p>
<p><strong>Use Cases:</strong></p>
<ul>
    <li>Explore and document your Data Lake</li>
    <li>Enable Athena to query S3 data</li>
    <li>Serve as a central metadata repository</li>
</ul>
<p><strong>Why is it relevant to AI/ML?</strong></p>
<p>Helps analysts, data scientists, and models access data with full context—knowing what each column, data type, and table means.</p>

<hr>

<h3>Glue DataBrew</h3>
<p><strong>What is it?</strong></p>
<p>A no-code visual tool to clean and prepare data. Supports common transformations like removing nulls, changing formats, or detecting outliers—all with clicks.</p>
<p><strong>Use Cases:</strong></p>
<ul>
    <li>Clean a dataset before training a model</li>
    <li>Convert formats (e.g., JSON to Parquet)</li>
    <li>Analyze data quality without writing code</li>
</ul>
<p><strong>Why is it relevant to AI/ML?</strong></p>
<p>Perfect for non-technical users or quick data exploration before building a full ETL pipeline.</p>

<hr>

<h3>Amazon Athena</h3>
<p><strong>What is it?</strong></p>
<p>A serverless service that lets you run SQL queries directly on data in S3—no infrastructure needed.</p>
<p><strong>Use Cases:</strong></p>
<ul>
    <li>Explore raw datasets before model training</li>
    <li>Validate ETL pipeline outputs</li>
    <li>Create ad-hoc reports on S3 data</li>
</ul>
<p><strong>Why is it relevant to AI/ML?</strong></p>
<p>Lets you understand your data before feeding it into a model—helping identify patterns or quality issues early on.</p>

<hr>

<h3>AWS Step Functions</h3>
<p><strong>What is it?</strong></p>
<p>A workflow orchestration service that coordinates multiple AWS services in visual flows—ideal for full data pipelines.</p>
<p><strong>Use Cases:</strong></p>
<ul>
    <li>End-to-end pipeline: ingestion, transformation, model training</li>
    <li>Automate data validation workflows</li>
    <li>Coordinate tasks across Lambda, Glue, and SageMaker</li>
</ul>
<p><strong>Why is it relevant to AI/ML?</strong></p>
<p>Real-world ML projects aren’t isolated tasks. With Step Functions, you define the entire pipeline and keep things organized and traceable.</p>

<hr>

<h3>AWS DMS (Database Migration Service)</h3>
<p><strong>What is it?</strong></p>
<p>A service that migrates data from on-premises databases to AWS, or between AWS databases. Supports heterogeneous migrations (e.g., Oracle to PostgreSQL).</p>
<p><strong>Use Cases:</strong></p>
<ul>
    <li>Migrate historical data from on-prem Oracle to S3</li>
    <li>Move transactional DBs from MySQL to Aurora</li>
    <li>Replicate real-time changes from production DB to Data Lake</li>
</ul>
<p><strong>Why is it relevant to AI/ML?</strong></p>
<p>Training data often lives in existing databases. DMS makes it easy to extract and sync that data into AWS.</p>

<hr>

<h2>Hands-On: Build Your First Data Pipeline</h2>
<ol>
    <li>Create an S3 bucket called "ml-course-data"</li>
    <li>Upload <code>sales.csv</code></li>
    <li>Create an S3 trigger that invokes a Lambda function</li>
    <li>Lambda validates and triggers a Glue job</li>
    <li>Glue transforms the data and saves it to "ml-course-data-cleaned"</li>
    <li>Query the results with Athena</li>
</ol>

<hr>

<h2>Conclusion</h2>
<p>Without good data, there’s no good Machine Learning. In AWS, S3 is the heart of the Data Lake—and services like Glue, Athena, and Kinesis complete the ecosystem.</p>
<p>In the next module, we’ll explore and clean that data before training a model.</p>
