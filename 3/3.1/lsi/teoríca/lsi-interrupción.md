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
- Modificación del /proc/sys/net/ipv4/tcp_max_syn.backlog siendo normalmente 128, si en el etc añadimos esta variable incrementada podemos aguantar más (un incremento excesivo puede causar la reducción de la calidad de servicio).
- Modificación de la variable /proc/sys/net/ipv4/tcp_synack_netmen esto maneja el time out del ack, reduciendo el tiempo de infección del flood.
- Uso de syn cookies para asegurar el sync mediante el suso de cookies, tcp.syncookies.
- syn proxy que filtra la comunicación syn, encargándose del handshake en lugar de la máquina y dándole la conexión establecida.
- syn caché que almacena lo mínimo necesario para la conexión, permitiendo mantener servicio durante el ataque.
## Udp flood
## Defensa
La defensa de los servicios web se suele realizar mediante el uso de reverse proxis y firewalls de estado.
### Pruebas de carga
- Apache bench
- Metev
# Conectividad Wifi
La conectividad es cuantificada por el RSSI, comenzando en 0 y bajando a los negativos cuando empeora la señal. Podemos observar estos valores con programas como ACRILIC.
## Bandas
Las principales bandas usadas son 2.4 y 5 GHz siendo el primero de mayor alcance y segundo de mayor potencia. En estas bandas de frecuencia tenemos dos estándares:
- Wifi 5.
- Wifi 6.
	- Sistema de atractivo de señales.