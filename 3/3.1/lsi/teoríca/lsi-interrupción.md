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
