<h1>Módulo # 8: Inteligencia Artificial Generativa (GenAI) en AWS</h1>

<h2>Objetivo</h2>
<p>En este módulo aprenderás qué es la Inteligencia Artificial Generativa, cómo ha evolucionado, qué servicios ofrece AWS para trabajar con ella, y cómo puedes aplicarla en proyectos reales de Machine Learning. También revisaremos sus principales casos de uso, retos y buenas prácticas.</p>

<hr>

<h2>¿Qué es la Inteligencia Artificial Generativa?</h2>
<p>La IA Generativa (GenAI) es una subdisciplina de la inteligencia artificial que se enfoca en la creación de contenido nuevo (texto, imágenes, audio, video, etc.) a partir de patrones aprendidos en datos históricos. 
A diferencia de modelos tradicionales que solo predicen o clasifican, los modelos generativos crean cosas nuevas.</p>

<hr>

<h2>Historia y Evolución de la IA Generativa</h2>
<p>Esta tecnología ha avanzado de forma acelerada. Algunos hitos clave:</p>
<ul>
    <li>🔹 Años 50-60: Primeros modelos probabilísticos basados en cadenas de Markov.</li>
    <li>🔹 Década de 1990: Popularización de los modelos n-gramas para generación de texto.</li>
    <li>🔹 2014: Ian Goodfellow introduce las GANs (Generative Adversarial Networks), revolucionando la generación de imágenes.</li>
    <li>🔹 2017: Google presenta el paper "Attention is All You Need", creando la arquitectura Transformer.</li>
    <li>🔹 2020+: Llegan modelos masivos como GPT-3, DALL·E y Stable Diffusion, llevando la IA Generativa al público masivo.</li>
</ul>

<hr>

<h2>¿Cómo funciona la IA Generativa?</h2>
<table border="1" cellpadding="5">
    <tr>
        <th>Fase</th>
        <th>Descripción</th>
    </tr>
    <tr>
        <td>Preentrenamiento</td>
        <td>El modelo se entrena sobre un dataset masivo y aprende patrones generales de lenguaje, imágenes o audio.</td>
    </tr>
    <tr>
        <td>Ajuste fino (Fine-Tuning)</td>
        <td>Se especializa el modelo con datos específicos de un dominio (legal, médico, financiero, etc.).</td>
    </tr>
    <tr>
        <td>Inferencia</td>
        <td>El modelo genera contenido en base a un <strong>prompt</strong> (instrucción o pregunta).</td>
    </tr>
</table>

<hr>

<h2>Servicios de AWS para IA Generativa</h2>
<p>AWS ofrece múltiples servicios para trabajar con GenAI, tanto para construir modelos como para consumir modelos preentrenados:</p>
<ul>
    <li>✅ <strong>Amazon Bedrock:</strong> Acceso a modelos fundacionales listos para usar, como Claude, Titan, Jurassic y Stable Diffusion.</li>
    <li>✅ <strong>SageMaker:</strong> Entrenamiento, ajuste fino y despliegue de modelos propios.</li>
    <li>✅ <strong>Comprehend:</strong> Análisis de texto con modelos preentrenados, útil para preprocesar datos antes de generar contenido.</li>
    <li>✅ <strong>Textract:</strong> Extracción automática de texto desde documentos escaneados (OCR), ideal para alimentar modelos generativos.</li>
</ul>

<hr>

<h2>Modelos Fundacionales en AWS</h2>
<table border="1" cellpadding="5">
    <tr>
        <th>Modelo</th>
        <th>Descripción</th>
        <th>Disponible en Bedrock</th>
    </tr>
    <tr><td>Claude (Anthropic)</td><td>Enfoque ético y seguro, optimizado para diálogos complejos.</td><td>✔️</td></tr>
    <tr><td>Titan (AWS)</td><td>Modelos de AWS enfocados en texto e imágenes.</td><td>✔️</td></tr>
    <tr><td>Stable Diffusion</td><td>Generación de imágenes a partir de texto.</td><td>✔️</td></tr>
    <tr><td>Jurassic (AI21)</td><td>Generación flexible de texto.</td><td>✔️</td></tr>
</table>

<hr>

<h2>Casos de Uso por Industria</h2>
<table border="1" cellpadding="5">
    <tr><th>Industria</th><th>Aplicaciones</th></tr>
    <tr><td>Retail</td><td>Descripción automática de productos, generación de reseñas, atención al cliente.</td></tr>
    <tr><td>Salud</td><td>Resúmenes de historiales clínicos, generación de informes médicos.</td></tr>
    <tr><td>Finanzas</td><td>Generación y análisis de contratos, explicación de productos financieros.</td></tr>
    <tr><td>Medios</td><td>Creación de guiones, generación de videos o piezas creativas.</td></tr>
    <tr><td>Legal</td><td>Generación de cláusulas contractuales basadas en plantillas.</td></tr>
</table>

<hr>

<h2>Pipeline Completo de GenAI en AWS</h2>
<ol>
    <li>Recolectar datos en S3 (texto, imágenes, audio, etc.).</li>
    <li>Anotar datos usando SageMaker Ground Truth.</li>
    <li>Entrenar o ajustar un modelo en SageMaker.</li>
    <li>Desplegarlo como endpoint en Bedrock o SageMaker.</li>
    <li>Configurar monitoreo de calidad con Model Monitor.</li>
    <li>Orquestar todo con Step Functions.</li>
</ol>

<hr>

<h2>Retos Comunes</h2>
<ul>
    <li>⚠️ Alucinaciones: El modelo puede inventar respuestas falsas.</li>
    <li>⚠️ Sesgos: Si el dataset está sesgado, el modelo lo amplifica.</li>
    <li>⚠️ Costos: Modelos grandes consumen mucho cómputo.</li>
    <li>⚠️ Seguridad: Vulnerable a ataques de inyección de prompts.</li>
    <li>⚠️ Cumplimiento: Difícil asegurar cumplimiento (GDPR, HIPAA).</li>
</ul>

<hr>

<h2>Buenas Prácticas</h2>
<ul>
    <li>✅ Evaluar si realmente necesitas GenAI o un modelo más simple es suficiente.</li>
    <li>✅ Elegir el modelo adecuado según el caso de uso.</li>
    <li>✅ Validar y sanitizar los prompts antes de enviarlos al modelo.</li>
    <li>✅ Monitorear outputs para detectar sesgos o respuestas inapropiadas.</li>
    <li>✅ Registrar inputs y outputs para auditoría.</li>
    <li>✅ Usar instancias optimizadas para reducir costos.</li>
</ul>

<hr>

<h2>Métricas Clave para GenAI</h2>
<table border="1" cellpadding="5">
    <tr><th>Métrica</th><th>Descripción</th></tr>
    <tr><td>Perplexity</td><td>Qué tan bien el modelo predice el siguiente token.</td></tr>
    <tr><td>BLEU</td><td>Calidad de traducción (texto a texto).</td></tr>
    <tr><td>ROUGE</td><td>Cobertura de resúmenes (texto a resumen).</td></tr>
    <tr><td>FID</td><td>Calidad visual de imágenes generadas.</td></tr>
    <tr><td>Latencia</td><td>Tiempo por inferencia.</td></tr>
    <tr><td>Costo por inferencia</td><td>Costo de cada predicción.</td></tr>
</table>

<hr>

<h2>Práctica Recomendada</h2>
<p>Crea un chatbot usando Bedrock y Lambda que responda preguntas sobre productos de tu tienda ficticia. Evalúa:</p>
<ul>
    <li>📥 Calidad de respuestas.</li>
    <li>📊 Tiempos de respuesta.</li>
    <li>💰 Costo mensual estimado.</li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>La IA Generativa en AWS te permite acelerar innovación en múltiples industrias. Si aprendes a usarla correctamente, puedes transformar tus datos en ventaja competitiva real.</p>

<blockquote><em>"Con GenAI no solo analizamos datos, creamos el futuro con ellos."</em></blockquote>
