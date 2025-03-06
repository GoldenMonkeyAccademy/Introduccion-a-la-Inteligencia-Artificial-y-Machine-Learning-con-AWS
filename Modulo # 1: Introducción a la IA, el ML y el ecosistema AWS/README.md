<h1>Módulo 1: Introducción a la IA, el ML y el ecosistema AWS</h1>
<h2>Introducción</h2>
<p>Bienvenidos al primer módulo de este curso sobre <strong>Inteligencia Artificial y Machine Learning con AWS</strong>. 
Aquí exploraremos los conceptos fundamentales de Machine Learning, cómo impacta en nuestra vida diaria y 
por qué AWS es clave para democratizar el acceso a estas tecnologías.</p>

<hr>

<h2>¿Qué es la Inteligencia Artificial?</h2>

<p><strong>Inteligencia Artificial (IA)</strong> es un área de la informática que busca desarrollar sistemas capaces de realizar tareas que normalmente requieren inteligencia humana. 
Esto incluye entender lenguaje natural, reconocer imágenes, resolver problemas complejos, aprender de la experiencia y tomar decisiones.</p>

<p>En términos simples, la IA busca crear "máquinas inteligentes" que puedan:</p>
<ul>
    <li>Aprender de los datos (como un humano aprende de la experiencia).</li>
    <li>Adaptarse a nuevas situaciones.</li>
    <li>Automatizar decisiones sin intervención humana directa.</li>
</ul>

<p><strong>¿Cómo se logra esto?</strong></p>
<p>Dentro del gran campo de la IA, existen diferentes enfoques o subáreas. Una de las más exitosas es precisamente el <strong>Machine Learning</strong>, que consiste en enseñar a las computadoras a aprender directamente de los datos.</p>

<p>Para entender la relación, podemos verlo así:</p>
<ul>
    <li><strong>Inteligencia Artificial:</strong> El gran objetivo de crear máquinas inteligentes.</li>
    <li><strong>Machine Learning:</strong> Un conjunto de técnicas dentro de la IA para lograr ese objetivo.</li>
    <li><strong>Deep Learning:</strong> Un subconjunto de ML que usa redes neuronales profundas.</li>
</ul>

<p>💡 En este curso nos enfocaremos principalmente en Machine Learning, pero siempre dentro del contexto más amplio de la Inteligencia Artificial.</p>

<p>Con esta base, ahora sí podemos profundizar en qué es Machine Learning y cómo AWS nos ayuda a aplicar estas técnicas en el mundo real.</p>

<hr>


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
<hr>
<h2>Tipos de Machine Learning</h2>
<h3>1️⃣ Aprendizaje Supervisado</h3>
<p>En el aprendizaje supervisado, el modelo se entrena con datos donde ya conocemos la respuesta correcta. Cada ejemplo de entrenamiento incluye:
    <ul>
        <li>📥 Características o atributos (tamaño de la casa, número de habitaciones, ubicación).</li>
        <li>📤 Etiqueta o resultado (precio de la casa).</li>
    </ul>
    El objetivo es aprender una **relación matemática** entre esas características y la etiqueta, para que el modelo pueda predecir el resultado en ejemplos nuevos.
</p>
<p><strong>Ejemplos reales:</strong></p>
<ul>
    <li>Predecir el riesgo de impago de un cliente (etiqueta = "paga" o "no paga").</li>
    <li>Detectar si un email es spam o no.</li>
</ul>

<h3>2️⃣ Aprendizaje No Supervisado</h3>
<p>En este caso, no hay etiquetas conocidas. Solo tenemos características y el objetivo es encontrar **patrones ocultos o estructuras** en los datos.</p>
<p><strong>Ejemplos reales:</strong></p>
<ul>
    <li>Segmentar clientes en grupos según su comportamiento de compra.</li>
    <li>Detectar productos que suelen comprarse juntos (reglas de asociación).</li>
</ul>

<h3>3️⃣ Aprendizaje por Refuerzo</h3>
<p>Este es un enfoque completamente distinto, inspirado en cómo aprenden los humanos y animales. Aquí, un "agente" aprende interactuando con un entorno.</p>
<p>El agente ejecuta acciones, recibe recompensas o penalizaciones, y ajusta sus decisiones para maximizar esas recompensas en el futuro.</p>
<p><strong>Ejemplos reales:</strong></p>
<ul>
    <li>Un robot aprendiendo a caminar.</li>
    <li>Un algoritmo aprendiendo a jugar videojuegos (como AlphaGo de DeepMind).</li>
</ul>
<hr>
<h2>Algoritmos Clave de Machine Learning</h2>

<h3>📊 Algoritmos comunes para Aprendizaje Supervisado</h3>
<ul>
    <li><strong>Regresión Lineal:</strong> Un modelo simple que encuentra una línea recta que mejor explica la relación entre las características y el resultado. Ideal para predecir valores continuos (ventas, temperaturas, etc.).</li>
    <li><strong>Regresión Logística:</strong> Similar, pero enfocado en clasificaciones binarias. El modelo devuelve la probabilidad de que algo pertenezca a una categoría o la otra (spam/no spam, aprobado/rechazado).</li>
    <li><strong>Árboles de Decisión:</strong> Modelos que crean un "diagrama de decisiones", donde cada nodo representa una pregunta (¿La casa tiene más de 3 cuartos?) y cada rama lleva a un resultado.</li>
    <li><strong>Random Forest:</strong> Un conjunto (o bosque) de muchos árboles de decisión, cada uno entrenado con una parte diferente de los datos, para mejorar la precisión.</li>
    <li><strong>SVM (Support Vector Machines):</strong> Un algoritmo matemático que encuentra la mejor frontera posible entre dos clases. Es útil cuando los datos no son perfectamente separables.</li>
</ul>

<h3>📊 Algoritmos comunes para Aprendizaje No Supervisado</h3>
<ul>
    <li><strong>K-Means:</strong> Algoritmo de clustering que agrupa puntos similares en "k" grupos. Útil para segmentar clientes o productos.</li>
    <li><strong>DBSCAN:</strong> Similar a K-Means, pero detecta clusters de diferentes tamaños y forma irregular, lo cual es útil para datos reales más complejos.</li>
    <li><strong>PCA (Análisis de Componentes Principales):</strong> Algoritmo de reducción de dimensionalidad que identifica las variables más importantes y descarta las irrelevantes.</li>
    <li><strong>Apriori:</strong> Detecta reglas de asociación (si alguien compra pan, probablemente compre mantequilla) y es clave para análisis de cestas de compra.</li>
</ul>

<h3>📊 Algoritmos comunes para Aprendizaje por Refuerzo</h3>
<ul>
    <li><strong>Q-Learning:</strong> El agente aprende una tabla que le dice cuál es la mejor acción en cada situación.</li>
    <li><strong>Deep Q Networks (DQN):</strong> En vez de una tabla, usa una red neuronal para aprender estrategias más complejas.</li>
    <li><strong>Policy Gradient:</strong> El modelo aprende directamente cuál es la mejor política (conjunto de reglas de acción) para maximizar recompensas.</li>
    <li><strong>Actor-Critic:</strong> Una combinación poderosa donde un "actor" propone acciones y un "crítico" evalúa qué tan buenas fueron.</li>
</ul>

<hr>
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
<hr>

<h2>Configuración Básica del Entorno AWS</h2>
<p>Antes de empezar a entrenar modelos o trabajar con datos, es fundamental asegurarnos de que tienes un entorno básico correctamente configurado en AWS. 
Esto te permitirá realizar todos los ejercicios prácticos y seguir el curso sin interrupciones.</p>

<p>Estos son los pasos clave que necesitas completar:</p>

<ul>
    <li>✅ <strong>Crear una cuenta gratuita en AWS (Free Tier):</strong> 
    Si aún no tienes una cuenta, puedes registrarte gratuitamente y acceder a muchos servicios sin costo durante el primer año. 
    <br>🔗 <a href="https://aws.amazon.com/free/" target="_blank">Guía oficial para crear una cuenta AWS Free Tier</a></li>
    <li>✅ <strong>Configurar permisos con IAM (Identity and Access Management):</strong> 
    En AWS, cada acción requiere permisos específicos. Crearemos un rol con acceso a SageMaker, S3 y Glue, que son servicios clave para el ciclo de vida de Machine Learning. 
    <br>🔗 <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started.html" target="_blank">Introducción a IAM y cómo crear roles</a></li>
    <li>✅ <strong>Crear un bucket en S3:</strong> 
    S3 es el lugar donde almacenaremos nuestros datasets, modelos entrenados y otros artefactos. Tener este bucket preparado desde el inicio es esencial para trabajar sin interrupciones. 
    <br>🔗 <a href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/create-bucket-overview.html" target="_blank">Cómo crear un bucket en Amazon S3</a></li>
    <li>✅ <strong>Iniciar SageMaker Studio:</strong> 
    SageMaker Studio es el entorno visual donde exploraremos datos, entrenaremos modelos y realizaremos pruebas directamente desde la consola de AWS. 
    <br>🔗 <a href="https://docs.aws.amazon.com/sagemaker/latest/dg/gs-studio.html" target="_blank">Guía oficial para lanzar SageMaker Studio</a></li>
</ul>



<p>Sin esta configuración inicial, los ejercicios prácticos que haremos más adelante no funcionarían correctamente. 
Por eso, dedicarle unos minutos ahora a preparar tu entorno te ahorrará dolores de cabeza más adelante.</p>
<hr>


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
<hr>

<h2>💡 Bonus:¿Qué es una Red Neuronal?</h2>
<p>Una <strong>Red Neuronal Artificial</strong> es un modelo de Machine Learning inspirado en cómo funciona el cerebro humano. Está formada por capas de nodos (neuronas) conectadas entre sí:</p>

<ul>
    <li><strong>Capa de entrada:</strong> Recibe las características (por ejemplo, tamaño de la casa, ubicación, etc.).</li>
    <li><strong>Capas ocultas:</strong> Procesan la información combinando pesos y funciones matemáticas.</li>
    <li><strong>Capa de salida:</strong> Devuelve la predicción final (precio de la casa, sí/no, etc.).</li>
</ul>

<p>Las redes neuronales son muy flexibles y pueden resolver problemas complejos, pero necesitan muchos datos y mucha potencia de cómputo. 
Cuando la red tiene muchas capas ocultas, la llamamos <strong>Red Neuronal Profunda (Deep Neural Network).</strong></p>

<p>En este curso, usaremos redes neuronales cuando lleguemos a temas como visión por computadora o procesamiento de lenguaje natural.</p>
