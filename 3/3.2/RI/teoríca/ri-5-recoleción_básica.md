# Búsqueda booleana
Query con condiciones booleanas que permite la iteración entre términos, esto lleva a la reducción en tiempo al permitir búsquedas paralelas. Este modelo tiene deficiencias como la imprecisión de las querys y dificultad de formulación.
# Búsqueda por ranking
La recuperación de documentos basándose en su ranking para una dada query permitiendo mayor precisión.
## Modelo de espacio de vectores
Se hacen uso de representación de documentos y querys como vectores de conceptos, siendo la distancia del coseno la relevancia de un dado documento para una query. Para estos vectores existen los siguientes elementos:
- Pesos, permite determinar la importancia de los términos, los dos principales acercamientos son la frecuencia de término (TF) y frecuencia de documento inversa (IDF).