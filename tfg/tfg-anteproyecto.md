# Breve descripción
Los sistemas de conversión de texto a voz (TTS) surgieron inicialmente como sistemas de concatenación de grabaciones de sonidos individuales, conocidos como sistemas de selección de unidades (US-TTS). Sin embargo, este enfoque presentaba múltiples deficiencias en la cohesión y entonación de las voces generadas. Con la aparición del aprendizaje profundo (DL), estos primeros sistemas fueron mejorados para aumentar la cohesión vocal. Además, surgió un nuevo enfoque basado en la generación completa de voces mediante redes neuronales.

Este avance dio lugar a diversas arquitecturas de redes neuronales. Una de ellas emplea una única red de conexión directa entre el texto de entrada y el espectrograma de Mel de salida (una representación simplificada del audio que resalta las características de la voz humana), logrando resultados de alta fidelidad.

A pesar de estos progresos, la adopción de estas tecnologías ha sido lenta fuera del ámbito angloparlante, lo que ha provocado un retraso significativo en otros idiomas. En el caso del gallego, la tecnología TTS aún se basa en sistemas US-TTS, como Cotovía, desarrollado por la Universidad de Vigo. Esto plantea un problema claro: la falta de modelos TTS de alta fiabilidad y calidad para este idioma.

El objetivo de este proyecto es aplicar los avances recientes en aprendizaje profundo al gallego y desarrollar una biblioteca capaz de generar voces con un alto grado de fidelidad. Además, se busca permitir la selección de diferentes voces y la generación de nuevas voces a partir de grabaciones proporcionadas.

Los aspectos clave del proyecto serán la calidad de las voces generadas y su similitud con las voces originales. Para ello, se emplearán arquitecturas de probada eficacia en otros idiomas, como Tacotron 2 y DeepVoice 3.
# Objetivos concretos
El objetivo principal de este proyecto es abordar la problemática expuesta. Para ello, se establecen los siguientes subobjetivos:

- Analizar el estado del arte de los sistemas TTS.
- Aplicar avances en aprendizaje profundo (DL) a la conversión de texto a voz en idioma gallego.
- Desarrollar una biblioteca TTS de alta fidelidad que genere voces con calidad y naturalidad.
- Implementar la selección de diferentes voces y la generación de nuevas voces a partir de grabaciones proporcionadas.
- Garantizar que las voces generadas sean de alta calidad y mantengan una gran similitud con las originales.
# Método de trabajo
El proyecto seguirá un proceso de desarrollo en espiral, dada la estabilidad de sus requisitos. Este enfoque permitirá la creación de prototipos en cada ciclo, refinando progresivamente el desempeño del sistema TTS. Además, se utilizará la metodología Kanban para la gestión de tareas, promoviendo un desarrollo eficiente y ágil.

En el primer ciclo, se establecerá la arquitectura general de la aplicación y el método de comunicación entre el sistema de conversión y la interfaz de usuario. Esto será fundamental para proporcionar mayor flexibilidad en los ciclos de desarrollo posteriores.
# Fases principales
El desarrollo del proyecto se llevará a cabo en las siguientes fases:
1. Investigación y selección de arquitecturas.
	- Análisis del estado del arte en TTS: Se estudiarán las arquitecturas de redes neuronales más adecuadas para el proyecto.
	- Diseño de las redes neuronales para la generación de espectrogramas y vocoder: Con base en la investigación previa, se definirán las arquitecturas a utilizar en el generador de espectrogramas y el vocoder.
	- Diseño de la estructura software de la aplicación: Se establecerá la estructura del software que integrará el sistema TTS.
2. Preparación de datasets para el entrenamiento.
	- Búsqueda de datasets en gallego: Se recopilarán conjuntos de datos de audio con transcripciones en gallego, priorizando aquellos de acceso público que incluyan información detallada, como la sincronización fonética y los tiempos de pronunciación de las palabras.
	- Procesamiento y organización de los datos: Se ajustará el formato de los datos y se dividirán en conjuntos de entrenamiento, validación y prueba.
3. Desarrollo del sistema TTS.
	- Implementación, entrenamiento y pruebas del generador de espectrogramas.
	- Implementación, entrenamiento y pruebas del vocoder.
	- Evaluación de la calidad del sistema completo.
4. Implementación de la librería.

Cabe destacar que, durante todas las fases del proyecto, se gestionarán y monitorizarán las tareas en concordancia con la metodología Kanban.
# Material y medios necesarios
Para la realización del proyecto se hará uso de los siguientes recursos digitales:
- Python, lenguaje elegido para el sistema de conversión, dado las siguientes herramientas de desarrollo:
	- Pandas, librería para el manejo de sets de datos.
	- Numpy, librería matemática.
	- TensorFlow o PyTorch, librería para el desarrollo de aplicaciones de aprendizaje profundo.

Por otra parte, los recursos físicos necesarios para el proyecto son un ordenador para le desarrollo y acceso a sistemas de altas prestaciones, como los equipos del CESGA para el entrenamiento del sistema.
Vale, mi intención era este finde tener el anteproyecto ya avanzado y la semana que viene ponerme a empezar con el trabajo