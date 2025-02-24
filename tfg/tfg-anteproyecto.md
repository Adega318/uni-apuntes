# Breve descripción
Los sistemas de conversión de texto a voz (TTS) surgieron inicialmente como sistemas de concatenación de grabaciones de sonidos individuales, conocidos como sistemas de selección de unidades (US-TTS). Sin embargo, este enfoque presentaba múltiples deficiencias en la cohesión y entonación de las voces generadas. Con la aparición del aprendizaje profundo (DL), estos primeros sistemas fueron mejorados para aumentar la cohesión vocal. Además, surgió un nuevo enfoque basado en la generación completa de voces mediante redes neuronales.

Este avance dio lugar a diversas arquitecturas de redes neuronales. Una de ellas utiliza una única red de conexión directa entre el texto de entrada y el espectrograma de Mel de salida (una representación simplificada del audio que resalta las características de la voz humana), logrando resultados de alta fidelidad.

A pesar de estos progresos, la adopción de estas tecnologías ha sido lenta fuera del ámbito angloparlante, lo que ha provocado un retraso significativo en otros idiomas. En el caso del gallego, la tecnología TTS aún se basa en sistemas US-TTS, como Cotovía, desarrollado por la Universidad de Vigo. Esto plantea un problema claro: la falta de modelos TTS de alta fiabilidad y calidad para este idioma.

El objetivo de este proyecto es aplicar los avances recientes en aprendizaje profundo al gallego y desarrollar una biblioteca capaz de generar voces con un alto grado de fidelidad. Además, se busca permitir la selección de diferentes voces y la generación de nuevas voces a partir de grabaciones proporcionadas.

Los aspectos clave del proyecto serán la calidad de las voces generadas y su similitud con las voces originales. Para ello, se emplearán arquitecturas de probada eficacia en otros idiomas, como Tacotron 2 y DeepVoice 3.
# Objetivos concretos
Este proyecto tiene como principal objetivo la resolución de la problemática expuesta, para ello se presentan los siguientes subobjetivos:
- Estudiar el estado del arte de los sistemas TTS
- Implementar avances en DL en la conversión de texto a voz para el idioma gallego.
- Desarrollar una biblioteca TTS de alta fidelidad que permita la generación de voces con calidad y naturalidad.
- Permitir la selección de diferentes voces y la generación de nuevas voces a partir de grabaciones proporcionadas.
- Garantizar que las voces generadas sean de alta calidad y mantengan una gran similitud con las originales.


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