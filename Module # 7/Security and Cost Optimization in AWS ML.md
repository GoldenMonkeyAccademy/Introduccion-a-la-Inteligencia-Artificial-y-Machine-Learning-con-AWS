<h1>Module 7: Security and Cost Optimization in AWS ML</h1>

<h2>Objective</h2>
<p>In this module, you will learn how to protect your data, models, and machine learning pipelines within AWS. You will also learn key practices for optimizing costs during model training, storage, and deployment. A successful ML project is not only accurate—it’s secure and cost-efficient.</p>

<hr>

<h2>Security: Protecting Data and Models</h2>
<p>In a cloud environment, training data and models are valuable assets that must be properly secured. AWS offers multiple layers of protection:</p>

<h3>✅ Roles and Permissions (IAM)</h3>
<p>In AWS, each service (S3, SageMaker, Glue) requires specific permissions. Instead of using fixed credentials, AWS recommends assigning <strong>IAM roles</strong> with the minimum required permissions (Principle of Least Privilege).</p>
<ul>
    <li>💡 SageMaker needs its own role, with access to S3 (for data and models), ECR (containers), and CloudWatch (logs).</li>
    <li>💡 Glue needs permissions to read from S3 and write to the Data Catalog.</li>
    <li>💡 Data scientists can have roles with limited access (e.g., read-only or limited to specific buckets).</li>
</ul>

<h3>✅ Data Encryption</h3>
<p>Encryption is key to protecting data at rest (in S3) and in transit (between services). AWS offers:</p>
<ul>
    <li>🔐 <strong>S3 Encryption:</strong> Automatically encrypts each file uploaded to S3.</li>
    <li>🔐 <strong>KMS (Key Management Service):</strong> Allows you to create customer-managed encryption keys.</li>
    <li>🔐 SageMaker Endpoints can also encrypt stored or captured predictions for monitoring.</li>
</ul>

<h3>✅ Access Control with Lake Formation</h3>
<p>If you're managing a Data Lake, <strong>AWS Lake Formation</strong> enables centralized permission management at the table or column level. This is ideal for ensuring that only authorized users can access certain data (e.g., hiding sensitive info like names or credit cards).</p>

<hr>

<h2>Cost Optimization: Financial Best Practices</h2>
<p>Running ML in the cloud can get expensive if resource usage isn’t properly managed. These are the recommended strategies to save money without compromising quality:</p>

<h3>✅ Spot Instances for Training</h3>
<p><strong>Spot Instances</strong> are spare EC2 capacity that AWS sells at up to 70–90% discounts. If your training jobs can be interrupted and restarted (as is typical in batch jobs), they’re an excellent choice.</p>

<p><strong>Example:</strong></p>
<pre><code>
estimator = XGBoost(
    instance_type='ml.m5.large',
    use_spot_instances=True,
    max_wait=3600
)
</code></pre>

<h3>✅ Pause Endpoints Outside Business Hours</h3>
<p>A common mistake is keeping deployed models running all the time, even when they’re not being used. For internal projects or demos, you can:</p>
<ul>
    <li>⏸️ Automatically stop endpoints outside business hours.</li>
    <li>⚙️ Use SageMaker Serverless Inference (only pay per invocation).</li>
</ul>

<h3>✅ Choose the Right Instance Type</h3>
<p>Bigger is not always better. Understanding your model’s actual requirements is key:</p>
<ul>
    <li>📊 Small models (under 500MB): ml.m5.large or ml.c5.large.</li>
    <li>📈 Large models (GBs or deep learning networks): ml.p3 or ml.g5 (GPU-powered).</li>
    <li>💡 Lightweight models with sporadic traffic: SageMaker Serverless or AWS Lambda.</li>
</ul>

<h3>✅ Efficient Storage</h3>
<p>Raw data can remain in S3 Standard, but old models or historical datasets can be moved to S3 Glacier (cold storage), drastically reducing costs.</p>

<hr>

<h2>Best Practice: Secure and Efficient Setup</h2>
<p>As a practical exercise, we recommend following these steps:</p>
<ol>
    <li>✅ Create IAM policies specific to SageMaker, S3, and Glue (Least Privilege Principle).</li>
    <li>✅ Enable automatic encryption on your S3 buckets.</li>
    <li>✅ Train and deploy a model using a Spot Instance.</li>
    <li>✅ Schedule a Lambda event to pause the endpoint after business hours.</li>
    <li>✅ Analyze the pipeline’s total cost using <a href="https://aws.amazon.com/cost-management/" target="_blank">Cost Explorer</a>.</li>
</ol>

<hr>

<h2>Security and Cost Checklist</h2>
<p>Before closing out an ML project in AWS, review this checklist:</p>
<ul>
    <li>☑️ Are you using least-privilege roles?</li>
    <li>☑️ Are sensitive data encrypted?</li>
    <li>☑️ Do you have granular access control in the Data Lake?</li>
    <li>☑️ Have you optimized training instances?</li>
    <li>☑️ Do you regularly review your costs?</li>
    <li>☑️ Do you automate endpoint shutdowns?</li>
</ul>

<hr>

<h2>Helpful Links</h2>
<ul>
    <li><a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html" target="_blank">Introduction to AWS IAM</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/security.html" target="_blank">SageMaker Security Guide</a></li>
    <li><a href="https://aws.amazon.com/sagemaker/pricing/" target="_blank">SageMaker Pricing</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor-data-capture.html" target="_blank">Data Capture and Cost Monitoring</a></li>
</ul>

<hr>

<h2>Conclusion</h2>
<p>In real-world ML projects, security and cost are not optional—they are critical for success. 
By protecting your data and optimizing resources from the start, you’ll avoid incidents and build a workflow that’s both scalable and sustainable.</p>
<p>In the next module, we’ll wrap up the course with a general review and final tips for those seeking certification or applying these concepts in their day-to-day work.</p>
