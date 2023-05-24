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

# Recuperación
## Transacción
Una transacción es una acción que pasa por un estado incoherente, las transacciones deben de cumplir las propiedades ACID:
- Atomicidad, si una operación se refleja en la base de datos se reflejan todas.
- Consistencia, una transacción mantiene la coherencia de la base de datos.
- Aislamiento, las transacciones deben realizarse de manera concurrente pero no interferir entre ellas.
- Durabilidad, las transacciones exitosas permanecen en la base de datos.

#### Concurrencia
En la concurrencia de dos transacciones sobre el mismo dato podemos observar varios problemas:
- Pérdida de actualización, en este caso la consecuente actualización del dato produce la perdida de la primera actualización.
- Lectura sucia, se realiza una lectura de un dato modificado que es posteriormente hecho rollback.
- Lectura no repetible, necesidad de la doble lectura de un dato que es modificado por otra transacción en el proceso.
- Lectura fantasma, problemas en el acceso a arrays por la inserción y eliminación de elementos por parte de un proceso.

### Commit
Señaliza la exitosa fiscalización de una transacción.
### Rollback
Señaliza una transacción no exitosa y que sus cambios deben deshacerse.

### Estados

![[Pasted image 20230505120746.png]]

## Tipos de fallos
Tenemos varios tipos de fallos en el sistema de almacenamiento:
- Duros, fallos que daña el medio de almacenamiento.
- Suaves, perdida de datos en los almacenamientos volátiles.
- Software, fallos que alteran la consistencia de la base de datos.

## Recuperación Log
Mediante un registro lógico LOG mantiene constancia de la actividades de la base de datos, requiriendo su almacenamiento estable.
# Tags
#2- 
#2-2 
#bd 