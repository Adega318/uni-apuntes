# Introducción
Protocolo de mensajes de error, con mensajes de tipo:
- Ping
- Destino inalcanzable
- Redirect
- Fragmentación
- Tiempo excedido
![[Pasted image 20230420114014.png]]
# Ping
Mensaje de comprobación de conexión con un destino.
![[Pasted image 20230420114318.png]]
Se envía un mensaje eco request y se espera por el eco reply, obteniendo información por el numero de paquetes que regresan.
# Traceroute
Da la ruta de los paquetes hacia un destino.
El funcionamiento se basa en el uso del TTL  y UCP. Se manda un datagrama UCP al destino con TTL uno, cuando llegue al primer router morirá y se enviara de regreso un ICMP de error de TTL, esto continuara aumentando el TTL hasta llegar al destino, cuando llegue el mensaje de error de ICMP será en lugar de TTL un error de puerto.
# Tags
#2- 
#2-2 
#red 