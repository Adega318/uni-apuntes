Las complejidades a analizar son:
- Espacio, al tener un gran número de documentos con grandes vocabularios, pueden ocupar mucho espacio donde la mayor parte es irrelevante.
- Tiempo, el recorrido de los términos en el espacio, puede ser lenta por el gran número de los mismos.

Para resolverlas se hace uso de un índice invertido, donde creamos un índice de términos que llevan a documentos.
(algoritmo de inversión en memoria)
# Sorting-based
Al crear un índice invertido debemos almacenar los términos en un orden, se suelen usar:
- DocID
- TermID

Leer ‘Search Engines Information Retrieval in Practice’ sección 5.63 Map-Reduce
# Actualización dinámica
Para actualizar dinámicamente el índice se puede hacer uso de un índice auxiliar para evitar la reconstrucción del índice completo en las operaciones de inserción y eliminación, los datos del auxiliar serán indexados en un momento conveniente.
# Compresión
Al comprimir los índices permitimos el aumento de velocidad de cargado. Los principales acercamientos a la compresión de índices son:
- Codificación básica, se hace uso de códigos de peso menor para términos comunes.
- Compresión de índices, reducción del tamaño de los gaps entre términos.

Los principales sistemas de compresión son:
- Delta encoding, almacenamiento de los documentos como diferencias con el anterior.
- Bit-Aligned, almacenamiento de números usando el 0 como separador.
- Elias-y, cálculo del número usando kd y kr, mírate la diapo.
- Elias-delta, versión de elias-y con mejor desempeñó para números grandes.

```note!
mirar porque elias-delta toma 2log2(log2 K) +log2(k)
```

- Byte-Aligned, sistema de codificación con códigos de 1 a 4 bytes.
	- V-byte, uso del número más significativo para indicar si se debe leer otro byte, siendo el uno el indicativo de último byte y 0 de no último (**0**0000001**1**0000011, el primer 0 indica seguir leyendo y el uno del segundo byte fin)

```
Leer Croft seción 3.51 codificación UTF-8
```

- Skip Pointers, punteros introducidos al comienzo de una posting list para saltar a documentos de manera rápida.

```
Leer Croft pag 153-154 explicación del problema de dgaps con skip pointers
```

# Búsqueda con índice invertido
Para la búsqueda se le aplica a la query el mismo procesado que a los documentos, sobre los elementos de la query obtenidos:
- Se buscan en el diccionario.
- Se recupera la posting list
- Se realiza la operación.

## Métodos de procesado de términos
Para el procesamiento de los términos de la query tenemos:
- Document-At-A-Time, computado de cada documento de manera independiente con el uso de todos los términos para el cómputo de cada documento.
- Term-At-A-Time, computado de cada término para el conjunto de los documentos.