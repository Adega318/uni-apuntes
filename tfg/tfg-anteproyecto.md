# Breve descripción
Los sistemas de conversión de texto a voz (TTS) hicieron su primera aparición como sistemas de concatenación de grabaciones de sonidos individuales; este acercamiento al TTS consta de múltiples deficiencias en la cohesión y entonación de las voces generadas. Con el surgir del aprendizaje profundo (DL), estas primeras iteraciones recibieron mejoras para aumentar la cohesión de las voces; por otro lado, apareció un nuevo acercamiento centrado en la generación completa de las voces mediante redes neuronales.
Con este nuevo acercamiento surgieron múltiples arquitecturas de redes; una de estas nuevas arquitecturas fue la constituida por una única red de conexión directa entre texto de entrada y espectrograma de Mel (simplificación del audio para aislar las características de la voz humana) de salida, consiguiendo resultados con alta fidelidad.

Estos avances han tenido una lenta adopción fuera del idioma inglés, causando la problemática que este proyecto busca resolver: la falta de modelos de alta fidelidad y calidad de TTS para el idioma gallego.

El proyecto a realizar busca la implementación de los anteriormente mencionados avances en DL para el idioma gallego y, mediante ello, crear una librería capaz de generar voces con alto grado de fidelidad y selección de voces a usar junto con la generación de las mismas dadas unas grabaciones proporcionadas.

Los aspectos cruciales en el proyecto serán la calidad de las voces generadas y su similitud a la imitada, para lo cual se hará uso de arquitecturas altamente exitosas en su implementación en otros idiomas, como Tacotron 2 o DeepVoice 3.
# Objetivos concretos
Como objetivo el proyecto tiene la creación de una librería de TTS para el idioma galleo haciendo uso de los recientes avances en el campo del DL, teniendo el sistema las funciones de generación e imitación de voces. Para alcanzar este objetivo los siguientes objetivos secundarios serán necesarios:
- Estudio del estado del arte para sistemas TTS.
- Búsqueda de datasets relevantes para el proyecto y depurado de los mismos para su uso.
- Desarrollo de los modelos usados para la conversión de texto a voz.
# Método de trabajo
El proyecto hará uso de un proceso de desarrollo en espiral por los requisitos altamente estables del mismo; esto permitirá la realización de prototipos en los diferentes ciclos, refinando él desempeñó del sistema TTS. Por otro lado, se hará uso de la metodología kanban para la gestión de tareas y fomento del desarrollo eficiente.

Cabe destacar el primer ciclo donde se establecerá la arquitectura general de la aplicación y método de comunicación entre el sistema de conversión e interfaz de usuario, lo que será de gran ayuda al permitir mayor libertad en los consecutivos ciclos de desarrollo.
# Fases principales
Las fases de desarrollo serán las siguientes:
- Búsqueda de arquitecturas para el sistema.
	- Estudio del estado del arte en TTS, en esta fase se busca encontrar arquitecturas de redes neuronales adecuadas para el proyecto.
	- Diseño de las redes neuronales de generación de espectrograma y vcoder, con las arquitecturas encontradas anteriormente se diseñarán las usadas en el generador de espectrograma y vcoder.
	- Diseño de estructura software de la aplicación, alrededor del sistema TTS se diseñará la estructura software de la aplicación.
- Preparación de datasets para el uso en entrenamiento.
	- Búsqueda de datasets de audios asociados a sus transcripciones en gallego, se buscarán datasets de acceso público, priorizando aquellos con información extendida del texto entre la que se incluye el momento de pronunciación de las palabras e información fonética.
	- Preparación de los datos para su uso en las fases de entrenamiento, se ajustará el formato de los datos y dividirán en grupos de entrenamiento validación y test.
- Desarrollo del sistema TTS.
	- Implementación, entrenamiento y pruebas del sistema de generación de espectrograma.
	- Implementación, entrenamiento y pruebas del vcoder.
	- Comprobación de la calidad del sistema al completo.
- Implementación del front-end del sistema.

Cabe destacar que durante todas las fases establecidas se realizara establecimiento de tareas y seguimiento de tareas en acuerdo con la metodología Kanban.
# Material y medios necesarios
Para la realización del proyecto se hará uso de los siguientes recursos digitales:
- Python, lenguaje elegido para el sistema de conversión, dado las siguientes herramientas de desarrollo:
	- Pandas, librería para el manejo de sets de datos.
	- Numpy, librería matemática.
	- TensorFlow o PyTorch, librería para el desarrollo de aplicaciones de aprendizaje profundo.

Por otra parte, los recursos físicos necesarios para el proyecto son un ordenador para le desarrollo y acceso a sistemas de altas prestaciones, como los equipos del CESGA para el entrenamiento del sistema.
Vale, mi intención era este finde tener el anteproyecto ya avanzado y la semana que viene ponerme a empezar con el trabajo