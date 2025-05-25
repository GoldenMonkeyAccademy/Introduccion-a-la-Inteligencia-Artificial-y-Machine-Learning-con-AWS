<h1>Module 6: Model Deployment and Monitoring</h1>

<h2>Objective</h2>
<p>In this module, you will learn how to deploy a model to production, integrate it as an API for other applications to consume, and monitor its performance to detect issues such as data drift or performance degradation.</p>

<hr>

<h2>Why is deployment crucial?</h2>
<p>Training a model is just part of the journey. The real value is realized when the model becomes a usable service for other applications or users. For example:</p>
<ul>
    <li>📦 A recommendation model integrated into an e-commerce platform.</li>
    <li>📲 A classification model running inside a mobile app.</li>
    <li>📊 A predictive model powering real-time dashboards.</li>
</ul>

<hr>

<h2>Deployment options on AWS</h2>
<p>AWS offers several ways to expose models as inference endpoints. Each has its own advantages and ideal use cases:</p>

<table border="1">
<tr>
    <th>Option</th>
    <th>Description</th>
    <th>Ideal Use Cases</th>
</tr>
<tr>
    <td>SageMaker Endpoint</td>
    <td>Managed service that creates a REST API directly from a model trained in SageMaker.</td>
    <td>Models of any size, direct integration with SageMaker.</td>
</tr>
<tr>
    <td>AWS Lambda</td>
    <td>Serverless function that loads a model and responds to requests. Ideal for small models.</td>
    <td>Lightweight models (<50MB), quick and infrequent predictions.</td>
</tr>
<tr>
    <td>Amazon Fargate</td>
    <td>Model packaged as a container (Docker) and run on an ECS cluster without servers.</td>
    <td>Heavier models, or when you need full control over the runtime environment.</td>
</tr>
</table>

<hr>

<h2>Deploying with SageMaker Endpoint (Practical Example)</h2>
<p>If you trained a model in SageMaker, deploying it is straightforward:</p>

<pre><code>
from sagemaker.predictor import Predictor

predictor = xgb.deploy(
    instance_type='ml.m5.large',
    endpoint_name='my-model'
)
</code></pre>

<p>Once deployed, you can make predictions like this:</p>

<pre><code>
import json

payload = {'inputs': [[3.5, 1.2, 5.3, 1.8]]}  # Example using Iris data
response = predictor.predict(json.dumps(payload))
print(response)
</code></pre>

<hr>

<h2>How does the endpoint connect to other apps?</h2>
<p>A SageMaker Endpoint is a REST API. That means it can be consumed by:</p>
<ul>
    <li>📲 Mobile apps.</li>
    <li>🌐 Web applications (backend).</li>
    <li>📊 Dashboards and batch processes.</li>
</ul>

<p>Example using cURL:</p>
<pre><code>
curl -X POST \
     -H "Content-Type: application/json" \
     -d '{"inputs": [[3.5, 1.2, 5.3, 1.8]]}' \
     https://my-endpoint.amazonaws.com/invocations
</code></pre>

<hr>

<h2>What is Model Monitor?</h2>
<p><strong>SageMaker Model Monitor</strong> is a service that automatically reviews the traffic received by the endpoint and compares it against the original data profile (the data used to train the model).</p>

<h3>Problems it detects:</h3>
<ul>
    <li>🚨 Changes in variable distribution (data drift).</li>
    <li>🚨 Unexpected new values (categories that didn’t exist before).</li>
    <li>🚨 Data quality issues (missing or out-of-range values).</li>
</ul>

<h3>Setting up Model Monitor (Typical Workflow)</h3>
<ol>
    <li>✅ Capture prediction traffic (with Data Capture).</li>
    <li>✅ Create a baseline from original data (Training Data Baseline).</li>
    <li>✅ Create a schedule to run the monitor periodically.</li>
    <li>✅ Review alerts in CloudWatch.</li>
</ol>

<pre><code>
from sagemaker.model_monitor import DataCaptureConfig

predictor = xgb.deploy(
    instance_type='ml.m5.large',
    endpoint_name='my-model',
    data_capture_config=DataCaptureConfig(
        enable_capture=True,
        destination_s3_uri='s3://my-bucket/capture/',
        capture_options=['Request', 'Response']
    )
)
</code></pre>

<p>Later, the Data Capture connects to a monitoring job:</p>
<pre><code>
from sagemaker.model_monitor import DefaultModelMonitor

monitor = DefaultModelMonitor(
role=role,
instance\_count=1,
instance\_type='ml.m5.large',
volume\_size\_in\_gb=20,
max\_runtime\_in\_seconds=3600
)

monitor.schedule(
endpoint\_input=predictor.endpoint\_name,
output\_s3\_uri='s3://my-bucket/monitoring/',
schedule\_cron\_expression='cron(0 12 \* \* ? \*)'
) </code></pre>

<hr>

<h2>Integration with CloudWatch</h2>
<p>All logs, metrics, and alerts from SageMaker Model Monitor are automatically sent to <strong>Amazon CloudWatch</strong>. From there you can:</p>
<ul>
    <li>📊 Create monitoring dashboards.</li>
    <li>🔔 Configure alarms for drift issues.</li>
    <li>📥 Integrate with notifications (SNS, email, Slack).</li>
</ul>

<hr>

<h2>Best Practice: Complete Deployment + Monitoring</h2>
<ol>
    <li>✅ Train a model (e.g., using XGBoost).</li>
    <li>✅ Save the model in S3.</li>
    <li>✅ Create a SageMaker endpoint.</li>
    <li>✅ Make some test predictions (via Postman or Python).</li>
    <li>✅ Enable Data Capture and Model Monitor.</li>
    <li>✅ Review logs and metrics in CloudWatch.</li>
</ol>

<hr>

<h2>Helpful Links</h2>
<ul>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/deploy-model.html" target="_blank">Deploying models on SageMaker</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html" target="_blank">Model Monitor Documentation</a></li>
    <li><a href="https://docs.aws.amazon.com/cloudwatch/" target="_blank">Getting Started with CloudWatch</a></li>
</ul>

<hr>

<h2>Conclusion</h2>
<p>With this, you’ve deployed a real API-based model on AWS. 
Your model is now part of a full system, ready to be used by apps, reports, or any other consumers. 
And most importantly: it’s not a “black box,” because Model Monitor will help you detect if something starts to go wrong.</p>

<p>In the next module, we’ll learn how to secure the model and optimize costs to ensure it’s production-ready.</p>
