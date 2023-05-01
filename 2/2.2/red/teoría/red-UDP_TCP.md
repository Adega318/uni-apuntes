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
	- CWR, redución de la velocidad de trasmisión.
	- ECE, confirmación de la recepción de un ECN.
	- URG, puntero de urgencia válido.
	- ACK, número de ACK válido.
	- PSH, pasar los datos a la aplicación.
	- RST, reiniciar conexión.
	- SYN, sincronizar.
	- FIN, finalizar el envio de datos.
- Tamaño de ventana, 
- Checksum, comprobación de errores.
- Puntero de urgencia, trasmisión de datos urgentes.
- Opciones
- Data

## Conexión

![[Pasted image 20230425175742.png]]

### Establecimiento
El protocolo de establecimiento comienza con el envio de un mensaje SYM por el cliente con su nº de secuencia inicial (ISN), reciviendo un SYM del servidor con su ISN y un ACK para el SYM del cliente con su número de ISN + 1. El cliente confirmael SYM del servidor con ACK de numero igual al ISN del servidor + 1.
### Finalización
El protocolo de cierre comienza con una de las partes mandando un FIN con el numero de secuencia (SN), la otra parte responde con un ACK con SN + 1 y un FIN con su SN actual, el primero confirma el FIN con ACK.
### Tamaños de tramisión
A causa de las limitaciónes de los tamaños de trasmisión tenemos dos parametros:
- **MTU**, número máximo de bytes que se puden enviar por el nivel de enlace.
- **MSS**, número maximo de bytes de datos permitidos antes de la fragmentación.
	- es enviado en el SYN de una conexión por ambas partes.

### Estados
- TIME_WAIT,  espera de 2 veces el tiempo de vida de un paquete por el ACK.
- FIN_WAIT, espera a la respuesta de un FIN.
- CLOSE_WAIT, espera a la confirmación del FIN de respuesta.

## Segmentos de reset
El segmento de reset se produce cuando el flag RST se activa, pudiendo ser de estos dos modos:

![[Pasted image 20230425180322.png]]

# Tags
#2- 
#2-2 
#red 