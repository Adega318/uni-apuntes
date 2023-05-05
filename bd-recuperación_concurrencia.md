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
Cuando se produce un fallo se pueden perder acciones realizadas, esto se debe a que


Esto se puede evitar con  la comprobación de la llegada al estado esperado tras la operación y restauración a un estado consistente.
# Tags
#2- 
#2-2 
#bd 