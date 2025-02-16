# Breve descripción
Tradicionalmente, los sistemas de generación de voz se han basado en la composición de palabras pregrabadas, teniendo distintivos errores y en general baja credibilidad. Pero recientes avances en los sistemas de redes neuronales han permitido la generación de voces de mayor calidad y credibilidad bajo el coste de requerir grandes sets de entrenamiento.

El proyecto consiste en la utilización de estos avances en el campo para la creación de una aplicación de escritorio la cual mediante una red neuronal convierta texto a voz para el idioma gallego, otra función que tenía el sistema será que dada una serie de grabaciones de voz la imitación de la misma.

Los aspectos cruciales en el proyecto serán la calidad de las voces generadas y su similitud a la imitada, para lo cual se harán uso de arquitecturas altamente exitosas en su implementación en otros idiomas como Tacotron 2.
# Objetivos concretos
El objetivo principal es el desarrollo de una red neuronal capad de generar voces en gallega siguiendo un guion e imitando una voz dada y una aplicación para la interacción con la misma.
- Realizar un estudio del estado del arte de sistemas TTS.
- Búsqueda y formateo de datasets a usar en el entrenamiento.
- Diseño e implementación de modelos de redes neuronales en python.
	- Entrenamiento
	- Test
	- Validación
- Comprobación humana de los resultados generados por el sistema.
# Método de trabajo
El proyecto hará uso de un proceso de desarrollo en espiral, ya que el ciclo de implementación, entrenamiento y prueba inherente de las redes neuronalales se ajusta perfectamente a esta metodología, donde la libertad otorgada permite la iteración a través de los ciclos para la creación de prototipos funcionales. Por otro lado, se hará uso de la metodología kanban para la gestión de las tareas y fomento del desarrollo eficiente.

Cabe destacar el primer ciclo donde se establecerá la arquitectura general de la aplicación y método de comunicación entre el sistema de conversión e interfaz de usuario, lo que será de gran ayuda al permitir mayor libertad en los consecutivos ciclos de desarrollo.
# Fases principales
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