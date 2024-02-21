- Profesor mail: alfonso.landin@udc.es
- Tecnología: Apache lucene

# Índices y búsquedas
- Posting list, lista de elementos asociados a un término.
- Page rank, calificación de un elemento basándose en parámetros para su presentación preferencial.
- tf, número de veces que aparece un término en los documentos.
- cf, suma de los tf del término en todos los documentos.
- df, número de documentos en los que aparece el término.
- idf, inversa u otra métrica del df para la relevancia de df pequeños.
- Frase queris, querys donde se da importancia a la distancia entre los términos, para lo cual almacenamos las posiciones donde aparece la palabra y se calcula la distancia entre los términos.
# Lucene
## Term
Representación de una palabra del texto, compuesto por dos valores, el texto y donde aparece.
- compareTo(term), compara dos términos.

## DirectoryReader
Lector de directorios.
- open(Directory), devuelve un IndexReader que lee el directorio dado.
- indexExist(Directory), verdadero en caso de existir un índice.

## Index