<h1>Módulo 1: Introducción a la IA, el ML y el ecosistema AWS</h1>

<h2>Introducción</h2>
<p>Bienvenidos al primer módulo de este curso sobre <strong>Inteligencia Artificial y Machine Learning con AWS</strong>. 
Aquí exploraremos los conceptos fundamentales de Machine Learning, cómo impacta en nuestra vida diaria y 
por qué AWS es clave para democratizar el acceso a estas tecnologías.</p>

<h2>¿Qué es Machine Learning?</h2>

<p><strong>Machine Learning</strong>, o <strong>aprendizaje automático</strong>, es una rama de la <strong>inteligencia artificial</strong> 
que permite a las computadoras aprender patrones a partir de datos, sin necesidad de ser programadas explícitamente para cada tarea.</p>

<p>En un sistema tradicional, un programador define reglas fijas: “Si pasa X, entonces haz Y”. 
En cambio, en Machine Learning, el modelo analiza datos históricos, detecta patrones y aprende por sí mismo las reglas que explican esos datos.</p>

<h3>Un poco de historia</h3>
<p>El término <strong>Machine Learning</strong> fue acuñado por <strong>Arthur Samuel</strong> en 1959, 
cuando desarrolló un programa capaz de jugar Damas, mejorando su desempeño a medida que acumulaba partidas.</p>

<p>A lo largo de los años, esta idea evolucionó gracias a:</p>
<ul>
    <li>El crecimiento exponencial de los datos digitales.</li>
    <li>La mejora en la potencia computacional (especialmente GPUs).</li>
    <li>Avances matemáticos y en algoritmos de optimización.</li>
</ul>

<h3>¿Cómo encaja Machine Learning dentro de la Inteligencia Artificial?</h3>
<p>Para entender mejor el panorama completo, es útil visualizar cómo encajan los conceptos:</p>
<ul>
    <li><strong>Inteligencia Artificial (IA):</strong> Campo general que busca que las máquinas imiten la inteligencia humana.</li>
    <li><strong>Machine Learning (ML):</strong> Subcategoría de IA enfocada en aprender patrones directamente desde los datos.</li>
    <li><strong>Deep Learning (DL):</strong> Subconjunto de ML, basado en redes neuronales profundas, inspirado en el cerebro humano.</li>
</ul>

<p><img src="https://github.com/mrkali88/Introduccion-a-la-Inteligencia-Artificial-y-Machine-Learning-con-AWS/blob/main/images/artificial-intelligence_machine-learning_deep-learning_difference.png" alt="IA vs ML vs DL"></p>

<h3>Ejemplo práctico</h3>
<p>Imagina una app de streaming. En lugar de programar reglas fijas ("Si el usuario ve Matrix, recomiéndale Inception"), 
el sistema analiza miles de usuarios y aprende que aquellos que vieron Matrix también tienden a ver Inception. 
Ese proceso de descubrimiento automático es lo que hace tan potente a Machine Learning.</p>




<h2>Tipos de Machine Learning</h2>
<ul>
    <li><strong>Supervisado:</strong> El modelo se entrena con datos etiquetados, es decir, datos donde conocemos la respuesta correcta.
        <br>✅ Ejemplo: predecir el precio de una casa basado en su tamaño y ubicación.
        <br>📊 Algoritmos comunes:
        <ul>
            <li>Regresión Lineal (predicción de valores numéricos).</li>
            <li>Regresión Logística (clasificación binaria: sí/no).</li>
            <li>Árboles de Decisión y Random Forest.</li>
            <li>Support Vector Machines (SVM).</li>
        </ul>
    </li>
    <li><strong>No Supervisado:</strong> El modelo explora datos sin etiquetas y busca patrones ocultos.
        <br>✅ Ejemplo: segmentar clientes según su comportamiento de compra.
        <br>📊 Algoritmos comunes:
        <ul>
            <li>Clustering (K-Means, DBSCAN).</li>
            <li>Reducción de dimensionalidad (PCA - Análisis de Componentes Principales).</li>
            <li>Modelos de asociación (Apriori, FP-Growth).</li>
        </ul>
    </li>
    <li><strong>Aprendizaje por Refuerzo:</strong> El modelo aprende por prueba y error, recibiendo recompensas por decisiones correctas.
        <br>✅ Ejemplo: un coche autónomo que mejora su conducción tras cada simulación.
        <br>📊 Algoritmos comunes:
        <ul>
            <li>Q-Learning.</li>
            <li>Deep Q Networks (DQN).</li>
            <li>Policy Gradient Methods.</li>
            <li>Actor-Critic.</li>
        </ul>
    </li>
</ul>

<h2>Aplicaciones Reales de Machine Learning</h2>
<ul>
    <li>🚗 Autos Autónomos: reconocimiento de señales y peatones.</li>
    <li>📺 Recomendaciones en Netflix y Spotify.</li>
    <li>🔎 Motores de búsqueda como Google Search.</li>
    <li>🏦 Banca: detección de fraudes y evaluación crediticia.</li>
</ul>

<h2>AWS y la Democratización del ML</h2>
<p>Antes, trabajar con IA requería infraestructura costosa y equipos especializados. 
Ahora, gracias a <strong>AWS</strong>, cualquier empresa o persona puede crear modelos con servicios gestionados.</p>

<h3>Servicios clave de AWS para IA/ML</h3>
<ul>
    <li>✅ <strong>Amazon SageMaker:</strong> Plataforma completa para entrenar, optimizar, desplegar y monitorear modelos de Machine Learning.</li>
    <li>✅ <strong>Amazon Rekognition:</strong> Análisis automático de imágenes y videos (detección de objetos, caras, texto en imágenes, etc.).</li>
    <li>✅ <strong>Amazon Comprehend:</strong> Procesamiento de lenguaje natural (análisis de sentimientos, detección de entidades, temas, etc.).</li>
    <li>✅ <strong>Amazon Bedrock:</strong> Acceso directo a modelos fundacionales (Foundation Models) para IA Generativa.</li>
    <li>✅ <strong>Amazon Textract:</strong> Extracción automática de texto y datos estructurados desde documentos escaneados.</li>
    <li>✅ <strong>Amazon Transcribe:</strong> Servicio para convertir automáticamente audio a texto (Speech to Text).</li>
    <li>✅ <strong>Amazon Polly:</strong> Conversión de texto a voz (Text to Speech) usando voces naturales.</li>
    <li>✅ <strong>AWS Glue:</strong> Servicio ETL (Extract, Transform, Load) para preparar datos antes del modelado.</li>
    <li>✅ <strong>Amazon Kinesis:</strong> Ingesta de datos en tiempo real, útil para proyectos de ML en streaming.</li>
    <li>✅ <strong>Amazon Forecast:</strong> Servicio especializado en predicciones de series temporales (demandas, ventas, etc.).</li>
    <li>✅ <strong>Amazon Personalize:</strong> Servicio gestionado para crear sistemas de recomendación personalizados.</li>
</ul>


<h2>Configuración Básica del Entorno AWS</h2>
<ul>
    <li>✅ Crear cuenta gratuita en AWS.</li>
    <li>✅ Configurar permisos de IAM para SageMaker y S3.</li>
    <li>✅ Crear un bucket en S3.</li>
    <li>✅ Iniciar SageMaker Studio.</li>
</ul>

<h2>Conclusión y Próximos Pasos</h2>
<p>Con esto completamos la primera etapa: entendimos qué es Machine Learning, cómo se clasifica, 
cómo impacta en el día a día, y por qué AWS es una plataforma clave.</p>
<p>En el siguiente módulo, aprenderemos cómo preparar y transformar datos, uno de los pasos más importantes para lograr buenos modelos.</p>

<h2>📚 Material Complementario</h2>
<ul>
    <li>📄 Diapositivas resumen (PDF).</li>
    <li>📊 Infografía: ML Supervisado vs No Supervisado vs Refuerzo.</li>
    <li>🧰 Guía rápida de configuración en AWS.</li>
    <li>🔗 <a href="https://aws.amazon.com/es/blogs/machine-learning/" target="_blank">Blog oficial de AWS Machine Learning</a></li>
</ul>
