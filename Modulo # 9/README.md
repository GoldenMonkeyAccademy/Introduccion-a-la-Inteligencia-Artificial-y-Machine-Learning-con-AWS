<h1>Módulo 9: Introducción a la Inteligencia Artificial Generativa (GenAI) en AWS</h1>

<h2>Objetivo</h2>
<p>En este módulo conocerás qué es la Inteligencia Artificial Generativa (GenAI), cómo se diferencia del Machine Learning tradicional y cuáles son los servicios clave de AWS para implementar soluciones generativas.</p>

<hr>

<h2>¿Qué es la Inteligencia Artificial Generativa?</h2>
<p>La <strong>IA Generativa</strong> es una rama de la inteligencia artificial que se enfoca en crear contenido nuevo a partir de patrones aprendidos en datos históricos. A diferencia de los modelos tradicionales que predicen o clasifican, GenAI puede generar textos, imágenes, videos, música, código y más.</p>

<p>Ejemplos comunes incluyen:</p>
<ul>
    <li>✅ Creación de textos automáticos (chatbots avanzados).</li>
    <li>✅ Generación de imágenes a partir de descripciones (text-to-image).</li>
    <li>✅ Creación de videos, música o código.</li>
    <li>✅ Traducción y resumen de documentos.</li>
</ul>

<hr>

<h2>Comparativa: ML Tradicional vs IA Generativa</h2>
<table border="1" cellpadding="5" cellspacing="0">
    <tr>
        <th></th>
        <th>Machine Learning Tradicional</th>
        <th>IA Generativa</th>
    </tr>
    <tr>
        <td><strong>Entrenamiento</strong></td>
        <td>Aprende patrones para clasificar o predecir.</td>
        <td>Aprende patrones para crear contenido nuevo.</td>
    </tr>
    <tr>
        <td><strong>Ejemplos</strong></td>
        <td>Predecir precios, detectar fraudes.</td>
        <td>Generar textos, imágenes, videos.</td>
    </tr>
    <tr>
        <td><strong>Resultado</strong></td>
        <td>Etiqueta o valor numérico.</td>
        <td>Texto, imagen, audio o video.</td>
    </tr>
    <tr>
        <td><strong>Modelos típicos</strong></td>
        <td>XGBoost, Random Forest, Regresión.</td>
        <td>Transformers, Diffusion Models, GANs.</td>
    </tr>
</table>

<hr>

<h2>Fundamentos Técnicos: Tipos de Modelos Generativos</h2>
<ul>
    <li>🤖 <strong>Modelos de Lenguaje Grande (LLMs):</strong> Especializados en generación de texto. Ejemplos: GPT, Claude.</li>
    <li>🎨 <strong>Modelos de Difusión:</strong> Crean imágenes a partir de texto. Ejemplos: Stable Diffusion.</li>
    <li>🤝 <strong>GANs (Generative Adversarial Networks):</strong> Modelos que enfrentan dos redes para generar datos realistas.</li>
    <li>🧰 <strong>Autoencoders Variacionales (VAEs):</strong> Útiles para compresión y generación.</li>
</ul>

<hr>

<h2>GenAI en AWS: Servicios Clave</h2>
<p>AWS ha creado un ecosistema completo para que las empresas adopten GenAI de forma rápida y segura. Los servicios clave son:</p>

<table border="1" cellpadding="5" cellspacing="0">
    <tr>
        <th>Servicio</th>
        <th>¿Qué es?</th>
        <th>Casos de uso</th>
    </tr>
    <tr>
        <td><strong>Amazon Bedrock</strong></td>
        <td>Plataforma que ofrece acceso directo a modelos fundacionales (Foundation Models) de diferentes proveedores.</td>
        <td>Chatbots, generación de contenido, asistentes virtuales, análisis de texto.</td>
    </tr>
    <tr>
        <td><strong>SageMaker JumpStart</strong></td>
        <td>Repositorio con modelos preentrenados (incluyendo GenAI) listos para usar.</td>
        <td>Prototipado rápido de aplicaciones generativas.</td>
    </tr>
    <tr>
        <td><strong>SageMaker Studio</strong></td>
        <td>Entorno completo para personalizar y desplegar modelos generativos.</td>
        <td>Ajuste fino (fine-tuning) de modelos.</td>
    </tr>
    <tr>
        <td><strong>Amazon Comprehend</strong></td>
        <td>Procesamiento de texto con capacidades NLP predefinidas.</td>
        <td>Análisis de sentimientos, clasificación de texto, detección de entidades.</td>
    </tr>
</table>

<hr>

<h2>Práctica sugerida</h2>
<p>Te sugerimos crear un pequeño proyecto para aplicar lo aprendido:</p>
<ol>
    <li>✅ Acceder a Amazon Bedrock y probar un modelo fundacional para generación de texto.</li>
    <li>✅ Enviar un prompt para generar respuestas automáticas.</li>
    <li>✅ Usar SageMaker para ajustar un LLM (fine-tuning) con datos propios.</li>
</ol>

<hr>

<h2>Buenas Prácticas para GenAI en AWS</h2>
<ul>
    <li>✅ Usa modelos preentrenados para ahorrar costos y tiempo.</li>
    <li>✅ Aplica técnicas de prompt engineering para mejorar resultados.</li>
    <li>✅ Monitorea siempre el costo, ya que los modelos generativos pueden ser costosos.</li>
    <li>✅ Considera usar endpoints serverless para inferencias esporádicas.</li>
    <li>✅ Asegura datos sensibles usando cifrado en tránsito y en reposo.</li>
</ul>

<hr>

<h2>Enlaces Relevantes</h2>
<ul>
    <li><a href="https://docs.aws.amazon.com/bedrock/index.html" target="_blank">Documentación oficial de Amazon Bedrock</a></li>
    <li><a href="https://docs.aws.amazon.com/sagemaker/latest/dg/studio-jumpstart.html" target="_blank">Documentación de SageMaker JumpStart</a></li>
    <li><a href="https://aws.amazon.com/es/blogs/machine-learning/category/artificial-intelligence/generative-ai/" target="_blank">Blog de AWS sobre GenAI</a></li>
</ul>

<hr>

<h2>Conclusión</h2>
<p>La IA Generativa representa una revolución en la forma de crear contenido digital. AWS te da las herramientas para aprovechar su poder, 
combinando modelos de última generación, almacenamiento seguro y un ecosistema listo para producción.</p>

<p>Con este módulo, completas tu formación integral de IA/ML en AWS, abarcando desde los fundamentos hasta las tecnologías más avanzadas como GenAI.</p>

