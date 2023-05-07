# Dirección MAC
Direcciones únicas usadas para identificar dispositivos, 48 bits con:
- Primeros 24 como identificador (OUI).
- Últimos 24 par el fabricante.

Las tramas trasmitidas tienen una MAC de destino asignada, siendo FF:FF:FF:FF:FF:FF.
# ARP

![[Pasted image 20230507182459.png]]

ARP es la correspondencia entre IP 32 bits y MAC de 48 bits.
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

# Tags
#2- 
#2-2 
#red 