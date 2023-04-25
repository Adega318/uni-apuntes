
![[Pasted image 20230425211540.png]]

# Niveles y protocolos
- Conectador, repite las entradas en todas las salidas.
- Conmutador, repite las entradas en la sealida correspondiente.
- Puente, conexión punto a punto que es capaz de conbertir protocolos.

![[Pasted image 20230424171605.png]]

# Direción IP
Cadena de 32 bits que identifica al dispositivo en la red, con dos partes el id de rez y de host.
Tenemos cinco clases:
![[Pasted image 20230424171945.png]]

Tenemos dos categorias:
- Públicas, identifican un dispositivo en internet.
- Privadas, usadas para funcionamiento interno, sindo de tipo A B o C y requiriendo de un NAT para haceder a internet.
## Loopback
La dirección 127.0.0.1 se reserba para el localhost, siendo una interfaz para el envio de paquetes a la propia maquina.
## IPV4
Tres tipos de direciones de envio:
- unicast, unica maquina.
- brodcast, todas las maquinas (ultima ip de la red donde se trasmita).
- multicast, un grupo de maquinas.
(brodcast y multicast solo funcionan con UDP)
## DNS
Servicio que combierte dominios a direciones IP.

# Cabecera IP
Tamaño de paquete 60 bytes.
![[Pasted image 20230321133951.png]]
- TCP/IP
- Versión
- Longitud de la cabecera
- Tipo de servicio
- Longitud total
- identificación
- Flag y offset
- TTL (time to live), límite del número de routers por los que puede pasar un paquete.
- Protocolo
- Checksum de cabecera
- IP origen
- IP destino
- Opciones
	- enrutamiento
	- timestamp
	- lista estricta
	- lista difusa
	- NoOp
- Datos
# Subredes
Sirven para dividir una red en partes más pequeñas. Para ello se usan los bits de host, para ello se establecen un número de bits de host suficiente para el número de subredes, siendo mínimo 2.
- Identificador de subred, con los dos primeros bits del identificador de host sabemos la subred.
## Máscara de subred
La máscara de subred informa del número de bits de host. El número de bits a uno índica el número de bits de subred.
## Direcciones reservadas
Las direcciones reservadas son la de subred y la de broadcast. La primera en el rango es la de subred y la ultima es la de broadcast.
# DHCP
Asignado de ip en función de mac del pc, pudiendo ser:
- dinámica
- automática
Se diferencian en el tiempo que se guarda la asociación mac-ip en el sistema.
## Funcionamiento
Hay tres pasos en el asignado de una ip:
- Discobery, se manda un mensaje para descubrir el DHCP.
- Offer, mensaje del servidor ofreciendo una ip.
- Request, respuesta pidiendo una de las ofertas.
- Acknowledgement, confirmación del establecimiento de la ip.
### Link-local
# NAT
# PAT

# Tags
#2- 
#2-2 
#red