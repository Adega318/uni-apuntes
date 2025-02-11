# Breve descripción
En el entorno actual de software donde se han producido grandes desarrollos en la generación de voz mediante el uso de redes neuronales este proyecto busca traer estos avances tecnológicos al idioma gallego con la creación de una aplicación de escritorio que permita la conversión de texto a voz en gallego.
La principal función de la aplicación será la conversión de texto a voz, con la posibilidad de incorporar la imitación de voces durante el proyecto o a futuro.
# Objetivos concretos
El principal objetivo es el desarrollo de un sistema con la capacidad de la conversión de texto en gallego a voz, esto requiere de los siguientes objetivos:
- Estudio de sistemas y tecnologías existentes en el entorno de conversión de texto a voz y búsqueda de sets de datos adecuados.
- Diseño del sistema de conversión basándose en las arquitecturas estudiadas en la fase anterior.
- Implementación y entrenamiento del sistema de conversión, durante esta fase también se realizarán pruebas de calidad y rendimiento del sistema.
- Implementación del front-end y pruebas del sistema en diversos hardwares.

Con el estudio completado se podrá considerar la expansión de la funcionalidad del sistema con el añadido de la imitación de voces.
# Método de trabajo
La naturaleza de este proyecto genera dos ramas de desarrollo, la fachada y el sistema de conversión, las cuales tendrán una interfaz para la comunicación entre ellas, lo cual permite un desarrollo con alto nivel de agilidad.
Por lo anteriormente mencionado haremos uso de un desarrollo en espiral, el cual nos dará la capacidad de obtener funcionalidades básicas rápidamente, realizar pruebas en cada ciclo para el control de la calidad e incorporar feedback obtenido.
Este acercamiento es altamente beneficioso para el desarrollo del sistema de conversión por la libertad de modificación del mismo que nos proporciona.
# Fases principales
Dada la metodología de trabajo, las fases del desarrollo tendrán un aspecto cíclico dado que se repetirán en los diferentes ciclos del desarrollo.
- Investigación y diseño de la aplicación, esta fase consiste en el estudio de arquitecturas y el establecimiento de la usada durante el resto del proceso de desarrollo.
	- Establecimiento de la interfaz entre los componentes del sistema.
	- Creación de la arquitectura inicial del sistema de conversión.
	- Recopilación de sets de datos para entrenamiento.
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