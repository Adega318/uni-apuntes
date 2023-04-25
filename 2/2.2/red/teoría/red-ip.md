
![[Pasted image 20230425211540.png]]

# Cabecera IP

![[Pasted image 20230321133951.png]]

La cabecera IP tiene un tamaño de 20 bytes con un campo opcional que comparte espacio con los datos, teniendo los siguientes campos:
- TCP/IP.
- Versión, versión de IP.
- Longitud de la cabecera, número de palabras de 32 bits de la cabezera.
- Tipo de servicio.
	- DS, campo de 6 bites para la tecnica DS.
	- ECN, indicador de congestión.
- Longitud total, longitud del datagrama en bytes.
- Identificación, identifica el datagrama.
- Flag y offset, campos de fragmentación.
- TTL (time to live), límite del número de routers por los que puede pasar un paquete antes de ser descartado.
- Protocolo, protocolo usado en la capa de transporte.
- Checksum de cabecera, correción de errores en la cabecera.
- Origen y destino, IP con 32 bits cada una.
- Opciones.
	- enrutamiento
	- timestamp
	- lista estricta
	- lista difusa
	- NoOp
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