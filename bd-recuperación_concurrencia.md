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
## Fallos
Cuando se produce un fallo se pueden perder acciones realizadas, esto se debe a que en el proceso de realizar la acción se pasa por un estado inconsistente.
Estos fallos se pueden paliar con  la comprobación de la llegada al estado esperado tras la operación y restauración a un estado consistente.
## Transacción
Una transacción es una acción que pasa por un estado incoherente, las transacciones deben de cumplir las propiedades ACID:
- Atomicidad, si una operación se refleja en la base de datos se reflejan todas.
- Consistencia, una transacción 
# Tags
#2- 
#2-2 
#bd 