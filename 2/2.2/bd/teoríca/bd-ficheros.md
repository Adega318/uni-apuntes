# Registros
Los archivos se organizan lógicamente como secuencias de registros, siendo conjuntos de valores referentes a los campos.
## Clave
Campo o conjunto de campos que identifican u ordenan registros, pudiendo ser:
- Externa, clave derivada del medio físico.
- Primaria, diferencian los registros.

## Longitud
### Fija
Se establece un tamaño fijo con facilidad de acceso pero falta de eficiencia. Con respecto a la gestión de borrados la manera de gestionar en la fija se establece el primer espacio como un puntero al primer libe y en los libres tener la dirección del siguiente, cuando se intenta insertar se sigue el camino hasta el ultimo puntero libre y se actualiza el penúltimo, cunado se borra se añade al final de la linea de libres el puntero liberado..
### Variable

![[Pasted image 20230426125955.png]]

La longitud es dinámica y se ajusta al contenido con mayor eficiencia pero peor acceso, teniendo tres tipos:
- Formato, cuando el formato varia se produce variaciones de tamaño.
- Campos, los campos tienen una longitud indefinida.
- Repetitivos, ciertos campos pueden repetirse cambiando el tamaño.

Para la gestión de borrados se organiza internamente los bloque con el número de registros seguidos de sus tamaños seguido del espacio libre y después los registros, de esta manera todo el espacio libre queda junto.
# Medio físico
## Bloques

![[Pasted image 20230426130350.png]]

Unidad de trasferencia de disco a memoria, conteniendo un número de registros. El tamaño de bloque se denomina factor de bloqueo y es un tamaño no perfecto, únicamente sabemos los imites para asignarlo:
- Inferior, impuesto para evitar la trasferencia excesiva de bloques.
- Superior, definido por el tiempo de trasmisión y tamaño del buffer.

# Organización de registros en archivos
## Montículo
Los ficheros son ordenados en función del orden de inserción, siendo favorecido por un alto factor de bloqueo.
### Lectura por clave
Para una clave N tenemos tres casos de funcionamiento:
- Único registro, lectura secuencial hasta encontrarlo.
- Varios registros, lectura completa del fichero.
- No registro, lectura completa y no se encuentra.

### Lectura ordenada

![[Pasted image 20230426131509.png]]![[Pasted image 20230426131548.png]]![[Pasted image 20230426131609.png]]

Leer ordenadamente los datos del fichero, se realiza mediante un merge sort dividiendo el ficheros en partes que entren en memoria, ordenándolas y uniéndolas para leerlas de manera ordenada.
## Ordenado

![[Pasted image 20230426132731.png]]

Sistema con recuperación rápida mediante un puntero en los registros al siguiente registro por orden de clave y con intento de localidad de bloque para claves cercanas. Este acercamiento ahorra el orden físico facilitando las operaciones de inserción  y borrado, únicamente necesitando reorganizar periódicamente para mantener la localidad.
Teniendo las siguiente operaciones:
- Leer clave, se puede establecer búsqueda binaria.
- Leer claves en orden, se sigue el puntero de primera a última.

## Hash
Acceso directo mediante un número de registro como clave externa, haciéndolo similar a un array unidimensional.
### Función hash
La función hash convierte el registro en un número de registro, teniendo tres características:
- uniforme y distribuido
- sensible
- evitar colisiones

Con respecto a las colisiones tenemos que tener en cuenta el factor de carga, calculado cómo $nº\ registros/Slots$ causando problemas cuando mas nos acerquemos a la ocupación total.
- Factor de carga, $Tamaño/ocupado$
### Manejo de sinónimos
#### Overflow
Fichero donde se inserten los sinónimos, pudiendo tener su propia organización.
#### Direccionamiento abierto
- Prueba lineal, se hacen saltos de un cuanto para buscar un slot vació donde almacenar el sinónimo, el problema es el proceso de búsqueda y reducción en la velocidad de lectura para sinónimos.
- Rehashing, se hace el hash con una segunda función para encontrar un slot alternativo, pudiendo repetir este rehash las veces necesarias $(H(K)+xD)mod N$, los problemas son la perdida del espacio vació y el desplazamiento arbitrario.

### Extensible

![[Pasted image 20230426135756.png]]

#### Proceso
1. Se aplica el hash sobre la hey.
2. Se toman los d primeros digitos del hash.
3. Se busca el puntero al bloque correspondiente al hash.
4. Se carga el bloque y se hace la operación.

#### Expansión y contracción
##### D
La expansión de la d se produce cuando se intenta insertar en un bloque lleno de d' igual a d, se aumenta en uno la d y funden los bloques. Por lo contrario, cuando la mayor d' es menor que d se produce contracción haciendo d igual a la mayor d'.
##### D'
La expansión de la d' se produce cuando se intenta insertar en un bloque lleno, se divide el bloque aumentando el hash del bloque y repartiendo los datos en el mismo entre dos bloques. La contracción, por lo contrario, se produce por el borrado mediante la fusión.
#### Refundido
Cuando dos bloques comparten en hash correspondiente a su mayor d' - 1 y sus contenidos caben en un único bloque, se fusionan en uno deduciendo la d'.
#### Borrado
Se extrae del bloque pertinente haciendo fusión y contracción en caso de ser necesario.
# Índices

![[Pasted image 20230522184153.png]]

Los índices permiten el acceso rápido en base a un campo de búsqueda.
- Campo de búsqueda, atributo o conjunto de los mismos que sirven para buscar.

## Clasificación
Accesos rápidos a datos de la base de datos, teniendo dos categorías:
- Primario, indexa la clave de ordenación del fichero de datos.
- Sin agrupación, indexa sobre cualquier campo, no necesariamente su clave.

También se caracterizan entre:
- Denso, una entrada por valor existente del campo o campos indexados.
- Escaso, sin una entrada por cada valor existente del campo o campos.

## Métricas de evaluación
Las métricas que se tiene en cuenta con respecto a un índice son:
- Tipos de accesos eficientes
- Tiempo de inserción
- Tiempo de borrado
- Coste espacial

## Árboles
Mejora sobre la búsqueda binaria, permitiendo descartar la mitad de nodos por cada nivel de profundidad.
### Heterogéneos

![[Pasted image 20230428101906.png]]

Los nodos se clasifican en hoja e intermedios, siendo:
- Hoja, apuntan a los registros del fichero.
- Intermedio, apuntan a otros nodos.

### Homogéneos

![[Pasted image 20230428101951.png]]

Único tipo de nodo que guarda un dato y siguientes nodos.

### Árbol B
Árbol de número mínimo de valores en cada nodo de **d** con máximo de **2d** y $2d+1$ punteros a datos.
#### Inserción
Se dará prioridad a las reorganizaciones antes que inserciones de nodos para mantener el tamaño del indice a mínimos.
#### Borrado
Al borrar en nodos hoja se eliminara la entrada en la hoja, si queda vacía se elimina el nodo.
Al borrar en nodos no hoja se elimina el elemento y se sube el valor de una hoja del mismo.
### Árbol B+

![[Pasted image 20230503135538.png]]

Se guardan duplicados en las hojas para facilitar la lectura ordenada.
# Selección de indices
La creación de un indice es un caso de costo entre la lectura del fichero y el uso de un indice.

# Tags
#2- 
#2-2 
#bd 
