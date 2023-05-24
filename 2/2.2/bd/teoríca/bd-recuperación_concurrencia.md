# Estructura de almacenamiento
Tenemos varios tipos de almacenamiento:
- Volátil, almacenamiento que no se mantiene tras la perdida de corriente del sistema.
- No volátil, almacenamiento que perdura tras la perdida de corriente.
- Estable, almacenamiento que puede sobrevivir a cualquier fallo basándose en replicas.

Cada proceso tiene su área de memoria.

![[Pasted image 20230505114221.png]]

Lo que lleva a las siguientes acciones:
- Leer, lectura del dato deseado y traslado de la misma al área del programa solicitante.
- Escritura, traslado del dato a memoria intermedia, con el Output realizado por el sistema de paginación en un tiempo indeterminado.

# Transacciones
## ACID
Propiedades para preservar la integridad de la base de datos:
- Atomicidad, todas las transacciones se reflejan correctamente.
- Consistencia, la ejecución en aislamiento preserva la consistencia.
- Aislamiento, todas las transacciones deben de ser independiente del resto y no influenciarse.
- Durabilidad, los datos producidos por una transacción permanecen tras la escritura.

## Commit y Rollback
- Comit, señala el fin de la transacción.
- Rollback, señala la transacción insatisfactoria y eliminación de los cambios.

## Estados

![[Pasted image 20230505120746.png]]

Los estados de las transacciones son:
- Activa, estado inicial de la transacción.
- Parcialmente comprometida, estado después de la escritura y antes de commit o rollback.
- Fallida, estado a causa de que no se puede realizar ejecución normal.
- Abortada, estado de revertir los cambios a causa del fallo.
- Comprometía, finalización con éxito.

# Recuperación
## Tipos de fallos
Tenemos varios tipos de fallos en el sistema de almacenamiento:
- Duros, fallos que daña el medio de almacenamiento.
- Suaves, perdida de datos en los almacenamientos volátiles.
- Software, fallos que alteran la consistencia de la base de datos.

## Recuperación Log
Mediante un registro lógico LOG mantiene constancia de la actividades de la base de datos, requiriendo su almacenamiento estable.

# Concurrencia
En la concurrencia de dos transacciones sobre el mismo dato podemos observar varios problemas:
- Pérdida de actualización, en este caso la consecuente actualización del dato produce la perdida de la primera actualización.
- Lectura sucia, se realiza una lectura de un dato modificado que es posteriormente hecho rollback.
- Lectura no repetible, necesidad de la doble lectura de un dato que es modificado por otra transacción en el proceso.
- Lectura fantasma, problemas en el acceso a arrays por la inserción y eliminación de elementos por parte de un proceso.

La concurrencia puede ser implementada de dos maneras:
- Planificación, se intercalan las operaciones de ambas transacciones.
- Planificación serie, se realizan las transacciones una a la vez.

Una transacción es serializadle si se puede hacer uso de ambas planificaciones sin que difieran el resultado y es necesario para que sea correcta la concurrencia.
## Protocolos basado en bloqueos
Existen dos tipos de bloqueo:
- Exclusivo (X), se reserva el recurso de manera exclusiva pudiendo leer y escribir.
- Compartido (S), se reserva el recurso para solo lectura por cualquiera.

Los elementos que se pueden bloquear son:
- Atributos de una tupla
- Tuplas
- Tablas
- Bloques

## Protocolo de bloqueo de 2 fases
### Normal
El modelo normal garantiza la serialidad con las siguiente fases.
1 Fase de crecimiento:
- transacciones pueden conseguir bloqueos o evolucionarlos de S a X.
- las transacciones no pueden liberar bloqueos.

2 Fase de decrecimiento:
- transacciones liberan bloqueos o los disminuyen de X a S.
- las transacciones no pueden conseguir bloqueos.

### Riguroso

![[Pasted image 20230524134634.png]]

1 Fase de crecimiento:
- transacciones pueden conseguir bloqueos o evolucionarlos de S a X.
- las transacciones no pueden liberar bloqueos.

2 Fase de decrecimiento en el final de la transacción:
- las transacciones pueden liberar bloqueos.

## Interbloqueo

![[Pasted image 20230524134709.png]]

### Prevención
La prevención del interbloqueo se puede basar en:
- Limite de tiempo, las transacciones tiene un limite de tiempo para realizar la transacción realizando un rollback en caso de time out.
	- Esperar-morir, cuando una transacción solicita un recurso de una transacción mas vieja hace rollback, si es más joven espera.
	- Herir-espera, cuando una transacción solicita un recurso de una transacción mas vieja espera, si es más joven la que este ocupando el dato suelta y espera.
### Detección
Al detectar interbloqueos se deben hacer rollbacks para corregir el bloqueo.
## Esquema multiversión

# Tags
#2- 
#2-2 
#bd 