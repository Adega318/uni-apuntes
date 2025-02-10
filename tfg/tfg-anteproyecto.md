# Breve descripción
En el entorno actual de software donde se han producido grandes desarrollos en la generación de voz en los últimos años este proyecto busca traer estos avances tecnológicos al idioma gallego con la creación de una aplicación que permita la conversión de texto a voz.
La aplicación consistirá de una página principal que permita la escritura de texto, generación de audio y reproducción del mismo.
Cabe destacar la adicción de funcionalidades sobre la capacidad principal anteriormente establecida, se espera añadir la imitación de voces mediante muestras, la cual residiría en una segunda página.
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
Para la realización del proyecto se hará uso de lo siguiente:
- Framework Spring Boot, framework para el desarrollo del backend en Java.
- Next.js, framework para el desarrollo del frontend en JavaScript.
- Python, lenguaje usado para el desarrollo del sistema de conversión

Por otra parte para el entrenamiento del sistema de conversión puede ser necesario el acceso a equipos de altas prestaciones.
# Borrador
# Breve descripción
El proyecto está centrada en la creación de una aplicación de conversión de texto a voz para el idioma Gallego. Contando de capacidades para la imitación de voces predefinidas y nuevas a partir de muestras de audio.
Además de lo anterior la aplicación contará con un sistema de valoración de las voces creadas para la documentación y próxima mejora del sistema.
# Objetivos concretos
El objetivo principal es dar una opción de calidad para la creación de voces en gallego, para llevarlo a cabo se requerirá cumplir los siguientes objetivos:
- Realizar un estudio de los sistemas existentes de conversión de texto a voz y buscar sets de datos útiles para nuestro caso de uso.
- Diseño del sistema de conversión, en lo que se considera la elección de arquitectura del sistema de conversión y metodología de entrenamiento, y aplicación, en lo que se considera la creación de diagramas de clases, modelado de bases de datos, ...
- Implementación del sistema y comprobación de la calidad del mismo en diferentes hardwares y sistemas operativos a través de pruebas de validación.
# Métodos de trabajo
El proyecto seguirá una metodología en espiral para centrarse en la creación del producto mínimo funcional y mejora del mismo a través del feedback. Cabe destacar que por la naturaleza del sistema este proyecto constara de dos desarrollos paralelos, la aplicación fachada y el sistema de conversión, esto se realizara de esta manera para facilitar la modificación y mejora del sistema de conversión.
# Fases principales
Las principales fases en el desarrollo serán:
- Investigación y diseño del sistema de conversión.
	- Establecimiento de arquitectura.
	- Recopilación de sets de datos.
- Diseño de la aplicación.
- Implementación del sistema de conversión y pruebas de calidad del mismo.
- Implementación de la aplicación.
# Material y medios necesarios
Para la realización del proyecto se hará uso de lo siguiente:
- Framework Spring Boot, framework para el desarrollo del backend en Java.
- Next.js, framework para el desarrollo del frontend en JavaScript.
- Python, lenguaje usado para el desarrollo del sistema de conversión

Por otra parte para el entrenamiento del sistema de conversión puede ser necesario el acceso a equipos de altas prestaciones.