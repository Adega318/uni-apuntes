# UDP

![[Pasted image 20230425131934.png]]

Protocolo de nivel de transporte basado en datagramas, sin garantizar llegada y multiplexando los datos y efectuando comprobación de errores sin:
- control de flujo
- control de congestión
- retransmisión de datos perdidos
- conexión/desconexión
Es utilizado en los siguientes casos:
- Medios de trasmisión fiables
- Aplicación en tiempo real
- Mensajes regulares, no importa perder alguno.
- Si es multicast o broadcas
## Cadena UDP

![[Pasted image 20230425132549.png]]

Las cadenas UDP tienen una longitud de **8 bytes** con los siguientes campos:
- Origen, puerto desde el que se envía.
- Destino, puerto de destino.
- Longitud, Cadena UDP + Data.
- Checksum, control de errores sobre la cabeza y data de UDP.
# TCP
Protocolo de comunicación centrado en proporcionar un servicio de envió de datagramas fiable y orientado a la comunicación. La conexión es bidireccional y simultánea con las siguientes funciones:
- establecer y terminar conexiones
- gestionar buffers y control de flujo
- multiplexar el nivel de aplicación
- controlar errores
- control de congestión
La fiabilidad de TCP se implementa a trabes de :
- control de longitud de segmentos (información enviada)
- temporizador para el ACK de los segmentos
- comprobación de errores
- ordenación de los segmentos en el receptor
- control de flujo
## Cabecera TCP

![[Pasted image 20230425133832.png]]

Las cabeceras TCP son de **20 bytes** (parte obligatoria, 40 con opciones) con los siguientes campos:
- Origen, puerto de origen.
- Destino, puerto de destino.
- Número de secuencia, número de byte en el fujo de mensajes TCP.
- Número de ACK, siguiente número de secuencia que el emisor del ACK espera recivir.
- Longitud cabecera, tamaño de la cabecera con las opciones.
- Flags
	- CWR
	- ECE
	- URG
	- ACK
	- 
# Tags
#2- 
#2-2 
#red 