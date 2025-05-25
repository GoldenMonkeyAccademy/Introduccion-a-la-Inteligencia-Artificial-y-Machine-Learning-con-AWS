<h1>Module 1: Introduction to AI, ML, and the AWS Ecosystem</h1>

<h2>Introduction</h2>
<p>Welcome to the first module of this course on <strong>Artificial Intelligence and Machine Learning with AWS</strong>. 
Here, we’ll explore the fundamental concepts of Machine Learning, its impact on our daily lives, and why AWS is key in making these technologies accessible to everyone.</p>

<hr>

<h2>What is Artificial Intelligence?</h2>
<p><strong>Artificial Intelligence (AI)</strong> is a field of computer science focused on creating systems capable of performing tasks that typically require human intelligence—like understanding natural language, recognizing images, solving complex problems, learning from experience, and making decisions.</p>

<p>In simple terms, AI aims to create “intelligent machines” that can:</p>
<ul>
  <li>Learn from data (similar to how humans learn from experience)</li>
  <li>Adapt to new situations</li>
  <li>Automate decisions without human input</li>
</ul>

<p><strong>How is this achieved?</strong></p>
<p>Within AI, there are several approaches or subfields. One of the most successful is <strong>Machine Learning (ML)</strong>, which involves teaching computers to learn directly from data.</p>

<p>To understand their relationship:</p>
<ul>
  <li><strong>Artificial Intelligence:</strong> The broad goal of building intelligent machines</li>
  <li><strong>Machine Learning:</strong> A set of techniques within AI used to achieve that goal</li>
  <li><strong>Deep Learning:</strong> A subset of ML that uses deep neural networks</li>
</ul>

<p>💡 In this course, we’ll focus primarily on Machine Learning, while always keeping the broader context of AI in mind.</p>

<p>Now that we’ve set the stage, let’s dive deeper into what Machine Learning is and how AWS helps us apply it in the real world.</p>

<hr>

<section>
  <h2>What is Machine Learning?</h2>
  <p>
    <strong>Machine Learning</strong> is a branch of <strong>Artificial Intelligence</strong> that enables computers to detect patterns and learn from data—without being explicitly programmed for every task.
  </p>
  <p>
    Traditional systems rely on hardcoded rules (e.g., “if X happens, then do Y”). ML systems analyze historical data, find patterns, and <strong>learn rules automatically</strong>.
  </p>

  <h3>🔍 Illustrative Example</h3>
  <p><strong>Problem:</strong> We want to classify emails as <code>spam</code> or <code>not spam</code>.</p>

  <h4>✅ Traditional Rule-Based Approach</h4>
  <pre><code># Manually written rules
def classify_email(email):
    if "win money fast" in email.lower():
        return "spam"
    elif "exclusive offer" in email.lower():
        return "spam"
    else:
        return "not spam"
  </code></pre>

  <p>This requires manually defining every rule—hard to maintain and scale.</p>

  <h4>🤖 Machine Learning Approach</h4>
  <pre><code>from sklearn.feature_extraction.text import CountVectorizer
from sklearn.naive_bayes import MultinomialNB

emails = ["Win money fast", "Exclusive offer just for you", "Meeting at 10", "Monthly report attached"]
labels = ["spam", "spam", "not spam", "not spam"]

vectorizer = CountVectorizer()
X = vectorizer.fit_transform(emails)

model = MultinomialNB()
model.fit(X, labels)

new_email = ["Win an exclusive offer today"]
X_new = vectorizer.transform(new_email)
print(model.predict(X_new))  # Output: ['spam']
  </code></pre>

  <p>The model learns which words commonly appear in spam and uses that knowledge to make predictions.</p>

  <p><strong>Conclusion:</strong> With ML, instead of writing manual rules, we let the system <em>learn from data</em>. This enables adaptability, scalability, and better performance on complex tasks.</p>
</section>

<h3>A Brief History</h3>
<p>The term <strong>Machine Learning</strong> was coined by <strong>Arthur Samuel</strong> in 1959. He developed a program that learned to play checkers and improved with each game.</p>
<p>Since then, ML has evolved due to:</p>
<ul>
  <li>Explosive growth in digital data</li>
  <li>Advances in computing power (especially GPUs)</li>
  <li>Progress in mathematics and optimization algorithms</li>
</ul>

<h3>How ML Fits into the AI Landscape</h3>
<p>To visualize how these concepts relate:</p>
<ul>
  <li><strong>Artificial Intelligence (AI):</strong> The overall field of making machines think like humans</li>
  <li><strong>Machine Learning (ML):</strong> A subfield focused on learning patterns from data</li>
  <li><strong>Deep Learning (DL):</strong> A subset of ML using deep neural networks inspired by the brain</li>
</ul>

<p><img src="https://github.com/mrkali88/Introduccion-a-la-Inteligencia-Artificial-y-Machine-Learning-con-AWS/blob/main/images/artificial-intelligence_machine-learning_deep-learning_difference.png" alt="AI vs ML vs DL"></p>

<h3>Practical Example</h3>
<p>Imagine a streaming app. Instead of coding specific rules ("if user watches Matrix, recommend Inception"), the system analyzes behavior across thousands of users and learns that those who watch Matrix also tend to watch Inception. That automatic discovery is what makes ML powerful.</p>

<hr>

<h2>Types of Machine Learning</h2>

<h3>1️⃣ Supervised Learning</h3>
<p>In supervised learning, the model is trained with data where the correct answer is known. Each example includes:</p>
<ul>
  <li>📥 Features (e.g., house size, number of rooms, location)</li>
  <li>📤 Label (e.g., house price)</li>
</ul>
<p>The goal is to learn a <strong>mathematical relationship</strong> between the inputs and the output.</p>
<p><strong>Real examples:</strong></p>
<ul>
  <li>Predicting whether a customer will default (label = “yes” or “no”)</li>
  <li>Classifying emails as spam or not</li>
</ul>

<h3>2️⃣ Unsupervised Learning</h3>
<p>No known labels—just features. The goal is to find <strong>hidden patterns or structures</strong>.</p>
<p><strong>Real examples:</strong></p>
<ul>
  <li>Segmenting customers by purchasing behavior</li>
  <li>Finding product combinations that are often bought together</li>
</ul>

<h3>3️⃣ Reinforcement Learning</h3>
<p>This is inspired by how humans and animals learn. An “agent” interacts with an environment, receives rewards or penalties, and learns to maximize future rewards.</p>
<p><strong>Real examples:</strong></p>
<ul>
  <li>Robots learning to walk</li>
  <li>Algorithms mastering video games (like DeepMind’s AlphaGo)</li>
</ul>

<hr>

<h2>Key Machine Learning Algorithms</h2>

<h3>📊 Common Algorithms for Supervised Learning</h3>
<ul>
  <li><strong>Linear Regression:</strong> Predicts continuous values like sales or temperatures using a straight line</li>
  <li><strong>Logistic Regression:</strong> Great for binary classification (e.g., spam vs. not spam)</li>
  <li><strong>Decision Trees:</strong> Models decisions using yes/no questions</li>
  <li><strong>Random Forest:</strong> An ensemble of decision trees for higher accuracy</li>
  <li><strong>SVM (Support Vector Machines):</strong> Finds the optimal boundary between classes</li>
</ul>

<h3>📊 Common Algorithms for Unsupervised Learning</h3>
<ul>
  <li><strong>K-Means:</strong> Clusters similar data into groups</li>
  <li><strong>DBSCAN:</strong> Finds irregularly shaped clusters</li>
  <li><strong>PCA (Principal Component Analysis):</strong> Reduces data dimensionality</li>
  <li><strong>Apriori:</strong> Discovers association rules (e.g., bread → butter)</li>
</ul>

<h3>📊 Common Algorithms for Reinforcement Learning</h3>
<ul>
  <li><strong>Q-Learning:</strong> Uses a table to learn the best action per situation</li>
  <li><strong>Deep Q Networks (DQN):</strong> Replaces the table with a neural network</li>
  <li><strong>Policy Gradient:</strong> Learns optimal strategies directly</li>
  <li><strong>Actor-Critic:</strong> Combines action-taking and evaluation</li>
</ul>

<hr>

<h2>Real-World Applications of Machine Learning</h2>
<ul>
  <li>🚗 Self-driving cars (traffic sign and pedestrian recognition)</li>
  <li>📺 Recommendations on Netflix or Spotify</li>
  <li>🔎 Search engines like Google</li>
  <li>🏦 Fraud detection and credit scoring in banking</li>
</ul>

<h2>AWS and the Democratization of ML</h2>
<p>In the past, AI required expensive infrastructure and expert teams. Thanks to <strong>AWS</strong>, anyone can now build ML models using managed services.</p>

<h3>Key AWS Services for AI/ML</h3>
<ul>
  <li><strong>Amazon SageMaker:</strong> End-to-end ML platform</li>
  <li><strong>Amazon Rekognition:</strong> Image and video analysis</li>
  <li><strong>Amazon Comprehend:</strong> Natural language processing</li>
  <li><strong>Amazon Bedrock:</strong> Access to foundation models for generative AI</li>
  <li><strong>Amazon Textract:</strong> Text extraction from scanned documents</li>
  <li><strong>Amazon Transcribe:</strong> Speech-to-text conversion</li>
  <li><strong>Amazon Polly:</strong> Text-to-speech with natural-sounding voices</li>
  <li><strong>AWS Glue:</strong> ETL service for preparing ML datasets</li>
  <li><strong>Amazon Kinesis:</strong> Real-time data streaming</li>
  <li><strong>Amazon Forecast:</strong> Time series forecasting (sales, demand)</li>
  <li><strong>Amazon Personalize:</strong> Custom recommendation engine</li>
</ul>

<hr>

<h2>Setting Up Your AWS Environment</h2>
<p>Before training models or working with data, it's important to have a properly configured AWS environment to ensure smooth progress through all exercises.</p>

<ul>
  <li><strong>Create an AWS Free Tier account:</strong>  
    <br>🔗 <a href="https://aws.amazon.com/free/" target="_blank">Sign up for AWS Free Tier</a></li>
  <li><strong>Configure IAM permissions:</strong>  
    <br>🔗 <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started.html" target="_blank">IAM getting started guide</a></li>
  <li><strong>Create an S3 bucket:</strong>  
    <br>🔗 <a href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/create-bucket-overview.html" target="_blank">How to create a bucket in Amazon S3</a></li>
  <li><strong>Launch SageMaker Studio:</strong>  
    <br>🔗 <a href="https://docs.aws.amazon.com/sagemaker/latest/dg/gs-studio.html" target="_blank">Getting started with SageMaker Studio</a></li>
</ul>

<hr>

<h2>Conclusion and Next Steps</h2>
<p>That wraps up the first part of the course. You’ve learned what ML is, how it’s categorized, how it’s changing industries, and why AWS plays such a big role.</p>
<p>Next up: we’ll learn how to prepare and transform data—one of the most important steps for building high-quality models.</p>

<h2>📚 Supplemental Materials</h2>
<ul>
  <li>📄 Summary slides (PDF)</li>
  <li>📊 Infographic: Supervised vs Unsupervised vs Reinforcement Learning</li>
  <li>🧰 Quick AWS setup guide</li>
  <li>🔗 <a href="https://aws.amazon.com/blogs/machine-learning/" target="_blank">Official AWS Machine Learning Blog</a></li>
</ul>

<hr>

<h2>💡 Bonus: What Is a Neural Network?</h2>
<p>A <strong>Neural Network</strong> is a Machine Learning model inspired by how the human brain works. It consists of layers of connected nodes (“neurons”):</p>

<ul>
  <li><strong>Input layer:</strong> Receives features (e.g., house size, location)</li>
  <li><strong>Hidden layers:</strong> Process data using weighted functions</li>
  <li><strong>Output layer:</strong> Returns the prediction (e.g., price, yes/no)</li>
</ul>

<p>Neural networks are powerful but require a lot of data and computing power. When they have many hidden layers, they’re called <strong>Deep Neural Networks</strong>.</p>

<p>In this course, we’ll explore neural networks in topics like computer vision and natural language processing.</p>
