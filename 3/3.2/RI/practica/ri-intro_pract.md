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

## IndexReader
Clase para el acceso a índices.
- close()
- maxDoc(), número máximo de documentos en el índice.
- numDoc(), número de documentos en el índice.
- docFrew(Term), número de documentos con el término.
- totalTermFreq(Term), número de apariciones del término en todos los documentos.
- getDocCount(string), número de documentos con el string.
- storeFields(), devuelve un StoredFields.
	- document(int), devuelve un Document por el ID.
		- Se le puede pasar un set de strings o un visitor para solo recuperar unos campos.
- termVectors(), devuelve un TermVectors.
	- get(int), devuelve el vector de términos del documento.
	- get(int, string), devuelve el vector de términos del documento y campo indicado.
- leaves(), devuelve las hojas del reader.
- getContext(), devuelve la raíz del árbol de readers.
- 