# Conceptos
## Clave
Campo o conjunto de campos que identifican u ordenan registros, pudiendo ser:
- Externa, clave derivada del medio físico.
- Primaria, diferencian los registros.
## Longitud
Podemos tener:
- Fija, se establece un tamaño fijo con facilidad de acceso pero falta de eficiencia.
- Variable, la longitud es dinámica y se ajusta al contenido con mayor eficiencia pero peor acceso, teniendo dos tipos:
	- Formato, cuando el formato varia se produce variaciones de tamaño.
	- Campos, los campos tienen una longitud indefinida.
	- Repetitivos, ciertos campos pueden repetirse cambiando el tamaño.
La gestión de borrados:
- Fija, la manera de gestionar en la fija se establece el primer espacio como un puntero al primer libe y en los libres tener la dirección del siguiente, cuando se intenta insertar se coge el primer libre y se cambia el puntero.
- Variable, se organiza internamente los bloque con el número de registros seguidos de sus tamaños seguido del espacio libre y después los registros, de esta manera todo el espacio libre queda junto.
# Medio físico
## Formato de archivo
## Bloques
- Factor de bloqueo, número de registros que entran en el bloque (limite superior e inferior en variable).
El tamaño de bloque debe de ajustarse para beneficiar a la operaciones más recurrentes.
# Organización de registros en archivos
# Indices
Accesos rápidos a datos de la base de datos.

# Tags
#2- 
#2-2 
#bd 
