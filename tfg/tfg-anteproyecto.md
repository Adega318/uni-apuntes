# Breve descripción
Los sistemas de conversisón de texto a voz (TTS) hicieron su primera aparición como sistemas de concatenación de grabaciones de las palabras individuales, entre estos sistemas encontramos ejemplos altamente utilizados como Loquendo. Estos sistemas tenían grandes problemas en la calidad del audio producido, siendo especialmente notable en las entonaciones planas y distinguible falta de cohesión, con el surgir del aprendizaje profundo (DL) estos sistemas recibieron grandes mejoras siendo principalmente por el aumento de la cohesión entre grabaciones. Para continuar mejorando la calidad de las voces generadas se crearon nuevas arquitecturas, descartando el uso de voces pregrabadas en favor de la generación completa, una de estas nuevas arquitecturas fue la constituida por una única red de conexión directa entre texto de entrada y espectrograma de Mel (simplificación del audio para aislar las características de la voz humana) de salida, consiguiendo resultados con alta fidelidad.

El proyecto a realizar busca la implementación de los anteriormente mencionados avances en DL para el idioma gallego y mediante ello crear una aplicación de escritorio TTS capaz de generar voces con alto grado de fidelidad y selección de voces a usar junto con la generación de las mismas dadas unas grabaciones proporcionadas.

Los aspectos cruciales en el proyecto serán la calidad de las voces generadas y su similitud a la imitada, para lo cual se harán uso de arquitecturas altamente exitosas en su implementación en otros idiomas como Tacotron 2 o DeepVoice 3.
# Objetivos concretos
Como objetivo el proyecto tiene la creación de un sistema TTS haciendo uso de los recientes avances en el campo del DL, teniendo el sistema las funciones de generación e imitación de vozes.
- Estudio del estado del arte para sistemas TTS.
	- Estudio de sistemas generadores de espectrograma de mel por texto
	- Estudio de vcoders (sistema que transforma el espectrograma a voz) con capacidad de imitar voces.
- Búsqueda de datasets relevantes para el proyecto y depurado de los mismos para su uso.
- Diseño de la arquitectura de los modelos e implementación de los mismos en python.
	- Entrenamiento del sistema de generación de espectrograma.
	- Test y validación del sitema de generación de espectrograma.
	- Entrenamiento del vcoder.
	- Test y validación del vcoder.
	- Comprobación humana de calidad de audio generado.
- Implementación de una interfaz para la interacción con el sistema.
# Método de trabajo
El proyecto hará uso de un proceso de desarrollo en espiral, ya que el ciclo de implementación, entrenamiento y prueba inherente de las redes neuronalales se ajusta perfectamente a esta metodología, donde la libertad otorgada permite la iteración a través de los ciclos para la creación de prototipos funcionales. Por otro lado, se hará uso de la metodología kanban para la gestión de las tareas y fomento del desarrollo eficiente.

Cabe destacar el primer ciclo donde se establecerá la arquitectura general de la aplicación y método de comunicación entre el sistema de conversión e interfaz de usuario, lo que será de gran ayuda al permitir mayor libertad en los consecutivos ciclos de desarrollo.
# Fases principales
Las fases de desarrollo serán las siguientes:
- Búsqueda de arquitecturas para el sistema.
	- Estudio del estado del arte en TTS.
	- Diseño de las redes neuronales de generación de espectrograma y vcoder.
	- Diseño de estructura software de la aplicación.
- Preparación de datasets para el uso en entrenamiento.
	- Búsqueda de datasets de audios asociados a sus transcripciones.
	- Preparación de los datos para su uso en las fases de entrenamiento.
- 

Dada la metodología de trabajo, las fases del desarrollo tendrán un aspecto cíclico dado que se repetirán en los diferentes ciclos del desarrollo.
- Investigación y diseño de la aplicación, esta fase consiste en el estudio de arquitecturas y el establecimiento de la usada durante el resto del proceso de desarrollo.
	- Establecimiento de la interfaz entre los componentes del sistema.
	- Creación de la arquitectura inicial del sistema de conversión.
	- Recopilación de sets de datos para entrenamiento.
	- Adecuación de los sets de datos.
- Fase cíclica, esta fase se repetirá en los múltiples ciclos durante el desarrollo de la aplicación.
	- Implementación del sistema de conversión.
	- Entrenamiento del sistema de conversión.
	- Pruebas de calidad y rendimiento sobre el sistema.
- Creación del front-end.
- Integración del sistema, pruebas finales y despliegue.
# Material y medios necesarios
Para la realización del proyecto se hará uso de los siguientes recursos digitales:
- Spring Boot, framework usado para el desarrollo del back-end del sistema en el lenguaje Java.
- Next.js, framework para el desarrollo del front-end del sistema en JavaScript.
- Python, lenguaje elegido para el sistema de conversión, dado las siguientes herramientas de desarrollo:
	- Pandas, librería para el manejo de sets de datos.
	- Numpy, librería matematica.
	- TensorFlow o PyTorch, librería para el desarrollo de aplicaciones de aprendizaje profundo.

Por otra parte, los recursos físicos necesarios para el proyecto son un ordenador para le desarrollo y acceso a sistemas de altas prestaciones, como los equipos del CESGA para el entrenamiento del sistema.