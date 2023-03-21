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
La máscara de subred informa del número de bits de host.
# Tags
#2- 
#2-2 
#red