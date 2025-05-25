<h1>Module #8: Generative Artificial Intelligence (GenAI) on AWS</h1>

<h2>Objective</h2>
<p>In this module, you’ll learn what Generative AI is, how it has evolved, what services AWS offers to work with it, and how to apply it in real-world machine learning projects. We’ll also review its main use cases, challenges, and best practices.</p>

<hr>

<h2>What is Generative Artificial Intelligence?</h2>
<p>Generative AI (GenAI) is a subfield of artificial intelligence focused on creating new content (text, images, audio, video, etc.) based on patterns learned from historical data.  
Unlike traditional models that only predict or classify, generative models create new things.</p>

<hr>

<h2>History and Evolution of Generative AI</h2>
<p>This technology has evolved rapidly. Some key milestones include:</p>
<ul>
    <li>🔹 1950s–60s: Early probabilistic models based on Markov chains.</li>
    <li>🔹 1990s: Popularization of n-gram models for text generation.</li>
    <li>🔹 2014: Ian Goodfellow introduces GANs (Generative Adversarial Networks), revolutionizing image generation.</li>
    <li>🔹 2017: Google publishes "Attention is All You Need," introducing the Transformer architecture.</li>
    <li>🔹 2020+: Arrival of massive models like GPT-3, DALL·E, and Stable Diffusion, bringing GenAI to mainstream audiences.</li>
</ul>

<hr>

<h2>How Does Generative AI Work?</h2>
<table border="1" cellpadding="5">
    <tr>
        <th>Phase</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>Pretraining</td>
        <td>The model is trained on a massive dataset to learn general patterns in language, images, or audio.</td>
    </tr>
    <tr>
        <td>Fine-Tuning</td>
        <td>The model is specialized using domain-specific data (legal, medical, financial, etc.).</td>
    </tr>
    <tr>
        <td>Inference</td>
        <td>The model generates content based on a <strong>prompt</strong> (instruction or question).</td>
    </tr>
</table>

<hr>

<h2>AWS Services for Generative AI</h2>
<p>AWS offers several services to work with GenAI, for both building your own models and using pre-trained ones:</p>
<ul>
    <li>✅ <strong>Amazon Bedrock:</strong> Access to ready-to-use foundation models like Claude, Titan, Jurassic, and Stable Diffusion.</li>
    <li>✅ <strong>SageMaker:</strong> Train, fine-tune, and deploy your own models.</li>
    <li>✅ <strong>Comprehend:</strong> Text analysis using pre-trained models—ideal for preprocessing before content generation.</li>
    <li>✅ <strong>Textract:</strong> Automatic text extraction from scanned documents (OCR), great for feeding generative models.</li>
</ul>

<hr>

<h2>Foundation Models on AWS</h2>
<table border="1" cellpadding="5">
    <tr>
        <th>Model</th>
        <th>Description</th>
        <th>Available in Bedrock</th>
    </tr>
    <tr><td>Claude (Anthropic)</td><td>Ethical and safety-focused, optimized for complex conversations.</td><td>✔️</td></tr>
    <tr><td>Titan (AWS)</td><td>AWS-native models focused on text and image generation.</td><td>✔️</td></tr>
    <tr><td>Stable Diffusion</td><td>Image generation from text prompts.</td><td>✔️</td></tr>
    <tr><td>Jurassic (AI21)</td><td>Flexible text generation.</td><td>✔️</td></tr>
</table>

<hr>

<h2>Use Cases by Industry</h2>
<table border="1" cellpadding="5">
    <tr><th>Industry</th><th>Applications</th></tr>
    <tr><td>Retail</td><td>Automated product descriptions, review generation, customer service chatbots.</td></tr>
    <tr><td>Healthcare</td><td>Summarizing medical histories, generating clinical reports.</td></tr>
    <tr><td>Finance</td><td>Contract generation and analysis, explanation of financial products.</td></tr>
    <tr><td>Media</td><td>Scriptwriting, video and creative content generation.</td></tr>
    <tr><td>Legal</td><td>Clause generation based on templates.</td></tr>
</table>

<hr>

<h2>End-to-End GenAI Pipeline on AWS</h2>
<ol>
    <li>Collect data in S3 (text, images, audio, etc.).</li>
    <li>Label data using SageMaker Ground Truth.</li>
    <li>Train or fine-tune a model in SageMaker.</li>
    <li>Deploy it as an endpoint in Bedrock or SageMaker.</li>
    <li>Set up quality monitoring with Model Monitor.</li>
    <li>Orchestrate the process using Step Functions.</li>
</ol>

<hr>

<h2>Common Challenges</h2>
<ul>
    <li>⚠️ Hallucinations: The model may generate false or made-up responses.</li>
    <li>⚠️ Bias: If the dataset is biased, the model will amplify it.</li>
    <li>⚠️ Costs: Large models are compute-intensive.</li>
    <li>⚠️ Security: Vulnerable to prompt injection attacks.</li>
    <li>⚠️ Compliance: Hard to guarantee adherence to regulations (e.g., GDPR, HIPAA).</li>
</ul>

<hr>

<h2>Best Practices</h2>
<ul>
    <li>✅ Evaluate whether you really need GenAI or a simpler model will suffice.</li>
    <li>✅ Choose the right model for your use case.</li>
    <li>✅ Sanitize and validate prompts before sending them to the model.</li>
    <li>✅ Monitor outputs for bias or inappropriate content.</li>
    <li>✅ Log inputs and outputs for auditing purposes.</li>
    <li>✅ Use optimized instances to reduce costs.</li>
</ul>

<hr>

<h2>Key Metrics for GenAI</h2>
<table border="1" cellpadding="5">
    <tr><th>Metric</th><th>Description</th></tr>
    <tr><td>Perplexity</td><td>How well the model predicts the next token.</td></tr>
    <tr><td>BLEU</td><td>Translation quality (text-to-text).</td></tr>
    <tr><td>ROUGE</td><td>Summary coverage (text-to-summary).</td></tr>
    <tr><td>FID</td><td>Visual quality of generated images.</td></tr>
    <tr><td>Latency</td><td>Time per inference.</td></tr>
    <tr><td>Cost per inference</td><td>Cost of each prediction.</td></tr>
</table>

<hr>

<h2>Recommended Practice</h2>
<p>Create a chatbot using Bedrock and Lambda that answers questions about products from your fictional store. Evaluate:</p>
<ul>
    <li>📥 Response quality.</li>
    <li>📊 Response time.</li>
    <li>💰 Estimated monthly cost.</li>
</ul>

<hr>

<h2>Conclusion</h2>
<p>Generative AI on AWS empowers you to accelerate innovation across industries. If used effectively, it can turn your data into real competitive advantage.</p>

<blockquote><em>"With GenAI, we don't just analyze data—we create the future with it."</em></blockquote>
