# Introducción
Con diferencia a las RNA se aporta en crudo los datos a la red para que un conjunto de capas se encarguen de extraer las características de los datos.
## Arquitecturas
Las principales arquitecturas son:
- Feed-Forward
- Feed-Back
- Bidireccionales

## Tipos de entrenamiento
A la hora de entrenar en función del número de datos etiquetados podemos usar:
- Puramente supervisado, se requiere de todos los datos supervisados.
- No supervisado en cada capa y supervisado en el nivel más alto, uso de datos etiquetados para el entrenamiento del clasificador final.
- No supervisado en cada capa y supervisado global, adición de una capa supervisada para un entrenamiento global.

El entrenamiento de estas redes tienen un problema a causa de la pérdida de la señal del backpropagation en causa de una alta longitud de red.
Para hacer el aprendizaje no supervisado de capas hacemos uso del greedy layer-wise training, usando aprendizaje no supervisado capa por capa, congelando las anteriores. Esto puede ser seguido de un entrenamiento final con datos etiquetados de una última capa o de la red al completo. Las capas usadas para este tipo de entrenamiento son las siguientes:
- Stacked Auto-Encoders, progresión de capas grandes a capas de menor tamaño para comprimir la información y posteriormente un descompresor, comprobando la preservación de la información, posteriormente se elimina el descompresor para obtener el vector de datos simplificados.
	- Denoising Auto-Encoders, uso de ruido en las entradas con la exigencia de salida sin ruido lleva a una tolerancia al ruido.
- Deep Belief Networks, redes con el uso de capas con conexiones bidireccionales, permitiendo alimentarle datos para obtener una salida e invertir el flujo para comprobar que se recuperan los datos originales.

# Redes convolucionales
Tipo de redes diseñadas para reconocer patrones visuales directamente de los píxeles con un preprocesado mínimo.
Las capas que componen estas redes se pueden caracterizar en tres tipos:
- Convolucionales, cada neurona toma datos de un conjunto cuadrado de la capa anterior realizando una convolución sobre las mismas.
- Max-Pooling, se reduce los valores de un cuadrado de la capa anterior a un único dato que va a la neurona de la siguiente capa.
- Totalmente conectadas, conecta con todas las neuronas de la capa anterior.

## Entrenamiento
El proceso de entrenamiento se basa en la propagación hacia atrás, requiriendo de grandes conjuntos de datos etiquetados.
# Modelos avanzados
- R-CNN
- Fast RCNN, usando una imagen como etrada de una CNN 
- YOLO, una única imagen es dividida en una rejilla donde se usa un algoritmo de búsqueda selectiva para tomar las regiones de interés, creando etiquetas para cada celda de la rejilla-