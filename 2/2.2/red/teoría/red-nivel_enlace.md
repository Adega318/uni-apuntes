# Dirección MAC
Direcciones únicas usadas para identificar dispositivos, 48 bits con:
- Primeros 24 como identificador (OUI).
- Últimos 24 par el fabricante.

Las tramas trasmitidas tienen una MAC de destino asignada, siendo FF:FF:FF:FF:FF:FF.
# ARP

![[Pasted image 20230507182459.png]]

ARP es la conversión de IP 32 bits a MAC de 48 bits y viceversa.
## Formato

![[Pasted image 20230507182947.png]]

El formato de un paquete ARP tiene los siguientes campos:
- Tipo de trama, ARP
- Tipo de HW, Ethernet
- Tipo de protocolo, IP
- Tamaño de dirección HW, 6 bytes
- Tamaño de dirección protocolo, 4 bytes
- Opciones, indica el tipo de operación (1 request, 2 reply)
- Direcciones
	- Ethernet origen
	- IP origen
	- Ethernet destino
	- IP destino

## Caché
Para evitar el uso excesivo del broadcast se mantiene en memoria las conversiones IP | MAC ya hechas, con un tiempo de vida.
# Tags
#2- 
#2-2 
#red 