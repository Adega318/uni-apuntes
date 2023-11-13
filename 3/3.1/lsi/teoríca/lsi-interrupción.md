# Lógicos
Explotación de vulnerabilidades para la interrupción de un servicio.
## Configuración
Errores lógicos originados en la configuración.
# Inundación
Denegación de servicio mediante la inundación de peticiones del servicio.
## Clusterizado
Defensa mediante el agrupamiento de conexiones y establecimiento de QoS.
## Factor de amplificación
Cantidad de peticiones recibidas en el destino por petición enviada.
## Conexión
Tenemos dos tipos de conexiones:
- Directa, se envían los paquetes al objetivo.
- Reflectivo, se envían a un gran servidor para que le llegue al objetivo las respuestas.
	- Protegido con el uso de firewals de control de estado, en UDP el control de estado debe de ser aplicado mediante la correspondencia de proceso y puerto, servicio y destino.
## Bot nets
Red de máquinas infectadas que bajo control que en un momento dado pueden atacar de manera coordinada.
## Syn flood
Inundación de la TCB para bloquear la comunicación tcp. Esto es mitigadle mediante:
- odificación del /proc/sys/net/ipv4/tcp_max_syn.backlog siendo normalmente 128, si en el etc añadimos esta variable incrementada podemos aguantar más (un incremento excesivo puede causar la reducción de la calidad de servicio). Otro método es la variable /proc/sys/net/ipv4/tcp_synack_netmen esto maneja el time out del ack, reduciendo el tiempo de infección del flood.