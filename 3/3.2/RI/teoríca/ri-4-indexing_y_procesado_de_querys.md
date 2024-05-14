Las complejidades a analizar son:
- Espacio, al tener un gran número de documentos con grandes vocabularios, pueden ocupar mucho espacio donde la mayor parte es irrelevante.
- Tiempo, el recorrido de los términos en el espacio, puede ser lenta por el gran número de los mismos.

Para resolverlas se hace uso de un índice invertido, donde creamos un índice de términos que llevan a documentos.
# Sorting-based
Al crear un índice invertido debemos almacenar los términos en un orden, se suelen usar:
- DocID
- TermID

# Actualización dinámica
Para actualizar dinámicamente el índice se puede hacer uso de un índice auxiliar para evitar la reconstrucción del índice completo en las operaciones de inserción y eliminación, los datos del auxiliar serán indexados en un momento conveniente o actualizar directamente el índice principal en caso de un número reducido de cambios.
# Compresión
Al comprimir los índices permitimos el aumento de velocidad de cargado. Los principales acercamientos a la compresión de índices son:
- Codificación básica, se hace uso de códigos de peso menor para términos comunes.
- Compresión de índices, reducción del tamaño de los gaps entre términos.

Los principales sistemas de compresión son:
- Delta encoding, almacenamiento de los documentos como diferencias con el anterior.
- Bit-Aligned, almacenamiento de números usando el 0 como separador.
- Elias-y, cálculo de codificación mediante:
	- $k_{d}=\log_{2}k$
	- $k_{r}=k-2^{k_{d}}$
	- La codificación del número k se realiza como $k_{d}$ codificado en unari seguido de $k_{r}$ codificado en binario en $k_{d}$ bits.
- Elias-δ, versión de elias-y con mejor desempeñó para números grandes.
	- $k_{d}=\log_{2}k$
	- $k_{r}=k-2^{k_{d}}$
	- $k_{dd}=\log_{2}(K_{d}+1)$
	- $k_{dr}=k_{d}+1-2^{k_{dd}}$
	- El número k se codifica como $k_{dd}$ en unari seguido de $k_{dr}$ en binario en $k_{dd}$ bits, seguido de $k_{r}$ en $k_{d}$ bits
- V-byte, uso del número más significativo para indicar si se debe leer otro byte, siendo el uno el indicativo de último byte y 0 de no último (**0**0000001**1**0000011, el primer 0 indica seguir leyendo y el uno del segundo byte fin)

Para la ayuda a la lectura eficiente de los índices se hace uso de **Skip Pointers**, punteros introducidos al comienzo de una posting list para saltar a documentos de manera rápida.
# Búsqueda con índice invertido
Para la búsqueda se le aplica a la query el mismo procesado que a los documentos, sobre los elementos de la query obtenidos:
- Se buscan en el diccionario.
- Se recupera la posting list
- Se realiza la operación.

## Métodos de procesado de términos
Para el procesamiento de los términos de la query tenemos:
- Document-At-A-Time, computado de cada documento de manera independiente con el uso de todos los términos para el cómputo de la puntuación de cada documento.
- Term-At-A-Time, se computa la puntuación de cada término para todos los documentos, acumulándolos en las puntuaciones de los documentos.

La primera es mucho más eficiente con respecto al uso de memoria, la no hacer uso de una tabla de acumuladores y la segunda tiene un menor acceso a memoria, la no tener que acceder a disco para recuperar las listas invertidas varias veces.
## Optimizaciones
Para optimizar el proceso se puede leer menos información de las listas invertidas (skip list) o calcular menos documentos (conjunctive processing).
- Skip list, lectura de querys teniendo en cuenta el tipo de términos para parar la búsqueda de manera temprana, saltándose partes.
- Conjunctive, ignorado de los documentos que no contienen el total de los términos o la mayoría en función de la predicción de la dificultad de la query.

Por otra parte, tenemos los métodos de límite, donde se descartan documentos que no superan una puntuación estimada mínima, eliminando los documentos por debajo de la misma. Para el cálculo de la puntuación estimada se puede usar el MaxScore, que toma la puntuación máxima de un término en un documento, permitiendo el descarte de documentos con baja puntuación para uno de los términos.

## Phrase query
Procesado de querys en la que se trata de mantener la relación entre los términos, la mejor manera es la existencia de índices invertidos de múltiples términos, pero es una opción muy costosa en espacio, siendo necesario el uso de bigrams parciales. Otra solución es el uso de índices con información posicional, permitiendo la búsqueda en los documentos con la condición de las posiciones de los términos en el documento.
# Correcciones
Empleo de correcciones en la escritura de la query.