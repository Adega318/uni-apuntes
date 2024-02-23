# Análisis de complejidad
Las complejidades a analizar son:
- Espacio, al tener un gran número de documentos con grandes vocabularios, pueden ocupar mucho espacio donde la mayor parte es irrelevante.
- Tiempo, el recorrido de los términos en el espacio, puede ser lenta por el gran número de los mismos.

## Índice invertido
Para resolverlas se hace uso de un índice invertido, donde creamos un índice de términos que llevan a documentos.
(algoritmo de inversión en memoria)
### Sorting-based
Al crear un índice invertido debemos almacenar los términos en un orden, se suelen usar:
- DocID
- TermID

### Actualización dinámica
Para actualizar dinámicamente el índice se puede hacer uso de un índice auxiliar para evitar la reconstrucción del índice completo en las operaciones de inserción y eliminación, los datos del auxiliar serán indexados en un momento conveniente.
### Compresión
