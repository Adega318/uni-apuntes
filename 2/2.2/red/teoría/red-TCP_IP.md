# Niveles y protocolos

![[Pasted image 20230425212011.png]]

- Conectador, repite las entradas en todas las salidas.
- Conmutador, repite las entradas en la salida correspondiente.
- Puente, conexión punto a punto que es capaz de convertir protocolos.

![[Pasted image 20230424171605.png]]

# Dirección IP
Cadena de 32 bits que identifica al dispositivo en la red, con dos partes, el id de red y de host.
Tenemos cinco clases:

![[Pasted image 20230424171945.png]]

Tenemos dos categorías:
- Públicas, identifican un dispositivo en internet.
- Privadas, usadas para funcionamiento interno, siendo de tipo A B o C y requiriendo de un NAT para acceder a internet.

Rangos de publicas y privadas:

|         | A                         | B                           | C                             |
| ------- | ------------------------- | --------------------------- | ----------------------------- |
| Publica | 1.0.0.0 - 126.255.255.255 | 128.0.0.0 - 191.255.255.255 | 192.0.0.0 - 223.255.255.255   |
| Privada | 10.0.0.0 - 10.255.255.255 | 172.16.0.0 - 172.31.255.255 | 192.168.0.0 - 192.168.255.255 | 


## Loopback
Las direcciones 127.0.0.1 - 127.255.255.254 se reservan para el localhost, siendo una interfaz para el envío de paquetes a la propia máquina.
## IPV4
Tres tipos de direcciones de envío:
- unicast, única máquina.
- brodcast, todas las maquinas (última IP de la red donde se trasmita).
- multicast, un grupo de máquinas.

(brodcast y multicast solo funcionan con UDP)
## DNS
Servicio que convierte dominios a direcciones IP.
# Tags
#2- 
#2-2 
#red 