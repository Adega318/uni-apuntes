
![[Pasted image 20230425211540.png]]

# Cabecera IP

![[Pasted image 20230321133951.png]]

La cabecera IP tiene un tamaño de 20 bytes con un campo opcional que comparte espacio con los datos, teniendo los siguientes campos:
- Versión, versión de IP.
- Longitud de la cabecera, número de palabras de 32 bits de la cabecera.
- Tipo de servicio.
	- DS, campo de 6 bites para la técnica DS.
	- ECN, indicador de congestión.
- Longitud total, longitud del datagrama en bytes.
- Identificación, identifica el datagrama.
- Flag y offset, campos de fragmentación.
- TTL (time to live), límite del número de routers por los que puede pasar un paquete antes de ser descartado.
- Protocolo, protocolo usado en la capa de transporte.
- Checksum de cabecera, corrección de errores en la cabecera.
- Origen y destino, IP con 32 bits cada una.
- Opciones.
	- enrutamiento
	- timestamp
	- lista estricta
	- lista difusa
	- NoOp

# Subredes

![[Pasted image 20230425213628.png]]

Sirven para dividir una red en partes más pequeñas. Para ello se utilizan los bits de host, para ello se establecen un número de bits de host suficiente para el número de subredes, siendo mínimo 2.
- Identificador de subred, con los dos primeros bits del identificador de host sabemos la subred.

## Máscara de subred

![[Pasted image 20230425213843.png]]

Indica los bits de red, subred y identificador de host, siendo los tres primeros bytes de red y el resto que estén a uno de subred y los ceros de host.
## Direcciones reservadas
Las direcciones reservadas son la de subred y la de broadcast, siendo la primera y última en rango respectivamente.
- Subred, dirección que identifica una red
- Broadcast, ip que representa todas las ips de la red.

## Tipos de repartos de subredes

![[Pasted image 20230425215334.png]]

### FLSM
El reparto de las subredes es del mismo tamaño para todas.
### VLSM
El reparto es correspondiente al tamaño requerido por la subred, calculándose con los siguientes pasos:
1. Ordenar las subredes de mayor a menor por número de equipos.
2. Elegir la más alta
3. Buscar la x que cumpla $Nºequipos <=2^{x}-2$
4. Calcular la máscara tomando un número de bits igual a la x para la subred del host.
5. Los bits de subred tomarán valores a partir del brodcast de la anterior subred, la primera comienza en el ID de red.
6. El rango comienza en todos los bits después de la máscara a 0 y termina con todos ellos a 1 (la primera y última reservadas).
7. Elige el siguiente valor y vuelve al paso 3.

# DHCP
Asignado de IP en función de mac del equipo, pudiendo ser:
- Estática, IP asignada basándose en la mac de manera permanente.
- Dinámica, IP asignada bajo solicitud por parte del equipo.
- Automática, dinámica pero para un mismo equipo siempre se asigna la misma IP.

## Funcionamiento
Hay tres pasos en el asignado de una IP:
- Discobery, se manda un mensaje para descubrir el DHCP.
- Offer, mensaje del servidor ofreciendo una IP.
- Request, respuesta pidiendo una de las ofertas.
- Acknowledgement, confirmación del establecimiento de la IP.

## Link-local
En caso de no haber un DHCP se puede usar un proceso link-local llamado APIPA permitiendo a un host auto-asignarse una IP para poder operar una LAN, se escoge una IP aleatoria y se comprueba su libertad con ARP.
# NAT
Protocolo que permite conbersión de IPs privadas a públicas al pasar por un router o firewall, existiendo dos tipos:
- PAT, múltiples máquinas comparten la misma IP pública.
- Basic NAT, cada privada tiene una pública.

# Tags
#2- 
#2-2 
#red