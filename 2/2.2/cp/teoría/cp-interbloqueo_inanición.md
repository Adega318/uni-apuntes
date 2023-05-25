# Interbloqueo
El interbloqueo es cuando dos o más threads esperan por recursos reservados por otros threads que esperan por recursos del primer grupo. Esto es consecuencia directa del mal uso de [[cp-seción_critica#Mutex|mutex]].
## Condiciones
Las siguientes son las condiciones necesarias para que se produzca un interbloqueo, es necesario que se cumplan simultáneamente.
- Exclusión mutua, recursos no compartibles.
- Hold and wait, se permite esperar con recursos reservados.
- No apropiación, El sistema operativo no puede forzar la liberación.
- Espera circular, procesos esperando por recursos que esperan por sus recursos.

## Soluciones
### Tratamiento
El interbloqueo se puede tratar mediante varias técnicas, algunas aplicadas por el sistema operativo, otras por el propio sistema concurrente. Esto depende principalmente del problema que lo produzca.
Algunos sistemas operativos (como Unix o Windows) ignoran el problema.
### Prevención
La manera de prevenir el interbloqueo es asegurar el incumplimiento de alguna de las condiciones del interbloqueo.
- Exclusión mutua, se puede evitar no permitiendo el acceso exclusivo a recursos.
- Hold and wait, se evita obligando a liberar los recursos reservados antes de esperar por nuevos.
- No acoplamiento, el uso del roll-back es la manera de resolver este tipo de problemas.
- Espera circular, para evitarlo se puede hacer uso de la espera ordenada, requiere el establecimiento de un orden de recursos.

# Inanición
Es el proceso de esperar un recurso sin conseguirlo. Esto se produce cuando un recurso no compartible es accedido por muchos procesos.
# Tags
#2-
#2-2
#cp