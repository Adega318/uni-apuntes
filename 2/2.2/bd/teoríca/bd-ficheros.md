# Registros
Los archivos se organizan lógicamente como secuencias de registros, siendo conjuntos de valores referentes a los campos.
## Clave
Campo o conjunto de campos que identifican u ordenan registros, pudiendo ser:
- Externa, clave derivada del medio físico.
- Primaria, diferencian los registros.
## Longitud
### Fija
Se establece un tamaño fijo con facilidad de acceso pero falta de eficiencia. Con respecto a la gestión de borrados la manera de gestionar en la fija se establece el primer espacio como un puntero al primer libe y en los libres tener la dirección del siguiente, cuando se intenta insertar se coge el primer libre y se cambia el puntero.
### Variable

![[Pasted image 20230426125955.png]]

La longitud es dinámica y se ajusta al contenido con mayor eficiencia pero peor acceso, teniendo dos tipos:
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
Los ficheros son ordenados en función del orden de inserción, siendo favorecido por un alto factor de bloqueo 
## Ordenado
## Hash
# Indices
## Clasificación
Accesos rápidos a datos de la base de datos, teniendo dos categorías:
- Primario, indexa la clave de ordenación del fichero de datos.
- Sin agrupación, indexa sobre cualquier campo, no necesariamente su clave.
También se caracterizan entre:
- Denso, una entrada por valor existente del campo o campos indexados.
- Escaso, sin una entrada por cada valor existente del campo o campos.
## Métricas de evaluación
## Árboles
Mejora sobre la búsqueda binaria, permitiendo descartar la mitad de nodos por cada nivel de profundidad.
### Heterogéneos

### Homogéneos

# Tags
#2- 
#2-2 
#bd 
