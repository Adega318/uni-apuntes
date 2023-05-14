# ICMP
## Introducción
Protocolo de mensajes de error de cabecera de 8 bytes, con mensajes de tipo:
- Ping
- Destino inalcanzable
- Redirect
- Fragmentación IP
- Tiempo excedido

![[Pasted image 20230420114014.png]]

## Ping
Mensaje de comprobación de conexión con un destino.

![[Pasted image 20230420114318.png]]

Se envía un mensaje ICMP eco request y se espera por el ICMP eco reply, obteniendo información por el numero de paquetes que regresan.
## Traceroute
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
	- MF, indica si no es el ultimo fragmento.
- Offset, indica el bite donde empieza el fragmento.
- Longitud, longitud total del fragmento, debiendo ser múltiplo de 8: Data + Transporte (UDP 8 o TCP 20) + IP (20)

## Error ICMP
Error producido cunado la fragmentación es requerida pero el paquete tiene DF a uno, incluyendo el MTU de la red y la cabecera del mensaje descartado.

![[Pasted image 20230425100446.png]]

## MTU discovery
Método de descubrir el mínimo MTU  de una comunicación, funciona mediante:
1. DF = 1
2. Tamaño que produce fragmentación.
3. Se recibe el ICMP
4. Se prueba con un tamaño menor.

## Proceso
### NFS (UDP)

![[Pasted image 20230507180752.png]]

Para una red con un MTU concreto se toma el tamaño de los datos NFS (múltiplo de 8) más la **cabecera UDP (8 bytes)**, Si el tamaño supera a MTU - 20.
$$UDP(8)+NFS>MTU-20$$
Si esto se cumple se fragmenta, se toma el MTU - 20 para darle el tamaño al NFS del primer datagrama.

Primero:
- identificador: original
- DF: 0
- MF: 1
- Offset: 0
- Long. total: Cab. IP + Cab UDP + Fragmento

Final:
- identificador: original
- DF: 0
- MF: 0
- Offset: Final del anterior (1480) /8
- Long. total: Cab. IP (20) + Cab UDP (8) + Fragmento

### HTTP (TCP)

![[Pasted image 20230507180812.png]]

Para un MTU se calcula el MSS (MTU - 20 -20), tamaño del HTTP. Se dividen en datagramas independientes.

Primero:
- identificador: original
- DF: 0
- MF: 0
- Offset: 0
- Long. total: Cab. IP (20) + Cab TCP (20) + Fragmento

Final:
- identificador: nuevo
- DF: 0
- MF: 0
- Offset: 0
- Long. total: Cab. IP (20) + Cab TCP (20) + Fragmento

# Tags
#2- 
#2-2 
#red 