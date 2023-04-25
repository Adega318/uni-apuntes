# Niveles y protocolos

![[Pasted image 20230425212011.png]]


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
# Tags
#2- 
#2-2 
#red 