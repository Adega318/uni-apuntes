# Introducción
Protocolo de mensajes de error, con mensajes de tipo:
- Ping
- Destino inalcanzable
- Redirect
- Fragmentación IP
- Tiempo excedido
![[Pasted image 20230420114014.png]]
# Ping
Mensaje de comprobación de conexión con un destino.
![[Pasted image 20230420114318.png]]
Se envía un mensaje eco request y se espera por el eco reply, obteniendo información por el numero de paquetes que regresan.
# Traceroute
Da la ruta de los paquetes hacia un destino.
El funcionamiento se basa en el uso del TTL  y UCP. Se manda un datagrama UCP al destino con TTL uno, cuando llegue al primer router morirá y se enviara de regreso un ICMP de error de TTL, esto continuara aumentando el TTL hasta llegar al destino, cuando llegue el mensaje de error de ICMP será en lugar de TTL un error de puerto.
# Fragmentación IP
- MTU, tamaño máximo de unidad que se permite pasar por una conexión.
Partición de los datagramas a causa del tamaño de trama, fragmentandolos con la misma cabecera y modificando el offset de fragmentación para cada fragmento.
![[Pasted image 20230420120149.png]]
Tenemos los siguientes campos:
- Identificación, valor único de cada datagrama.
- Flags
	- DF, indica la no fragmentación.
	- MF, indica si es el ultimo fragmento.
- Offset, indica el bite donde empieza el fragmento.
- Longitud, longitud total del fragmento, debiendo ser múltiplo de 8: Data + Transporte + IP(20)
## Error ICMP
Error producido cunado la fragmentación es requerida pero el paquete tiene DF a uno, incluyendo el MTU de la red y la ca

# Tags
#2- 
#2-2 
#red 