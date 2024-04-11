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
Para hacer el aprendizaje no supervisado de capas hacemos uso del greedy layer-wise traning, usando aprendizaje no supervisado capa por capa, congelando las anteriores. Esto puede ser seguido de un entrenamiento final con datos etiquetados de una última capa o de la red al completo. Las capas usadas para este tipo de entrenamiento son las siguientes:
- Stacked Auto-Encoders, progresión de capas grandes a capas de menor tamaño para comprimir la información y posteriormente un descompresor, comprobando la preservación de la información, posteriormente se elimina el descompresor para obtener el vector de datos simplificados.
	- Denoising Auto-Encoders, uso de ruido en las entradas con la exigencia de salida sin ruido lleva a una tolerancia al ruido.
- Deep Belief Networks, redes con el uso de capas con conexiones bidireccion
# Redes convolucionales
# Modelos avanzados