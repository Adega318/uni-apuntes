# Limitaciones V4
Las IPv4 tiene marcadas limitaciones:
- Pocas disponibles bajo el tamaño actual del Internet.
- Saturación del espacio de direcciones.
- Soporte limitado para las restricciones de calidad de servicio.
- Falta de mecanismos de seguridad en capa de red.

# Características V6

![[Pasted image 20230502180937.png]]

Las características de IPv6 son:
- Direcciones ampliadas y autoconfiguración.
	- 128 bits de direcciones.
	- autoconfiguración.
	- mejora de multicast y añadido de anycast.
- Simplificado de la cabecera
	- tamaño fijo de 40 bytes, Campos (6) + IP origen (16) + IP destino (16).
- Cabeceras de extensión.
- Seguridad, integrada de base en el protocolo.
- Etiquetas de flujo.
	- control de la calidad de servicio (QoS).

# Cabecera V6

![[Pasted image 20230502181036.png]]

La cabecera son siempre 40 bytes con los siguientes campos:
1. Versión (4 b), versión del protocolo.
2. Clase de tráfico (1 B), identifica la prioridad del paquete.
3. Etiqueta de flujo (20 b), permite agrupar paquetes bajo una misma etiqueta.
	- beneficioso para trafico multimedia.
4. Longitud de carga (2 B), longitud del paquete después de la cabecera (cabeceras de extensión + datos).
5. Cabecera siguiente (1 B), tipo de cabecera a continuación de la cabecera IP.
6. Limite de saltos (1 B), número de saltos restantes para el paquete.
7. Dirección origen (16 B)
8. Dirección destino (16 B), puede no ser el destino si esta la cabecera de enrutamiento.

# Direcciones V6
## Notación
Representada mediante 8 bloques de 16 bits en hexadecimal separados por ':', se eliminan los 0 a la izquierda y campos de 0 se representan con "::".
Crudo: FE80:0000:0000:0000:0202:B3FF:FE1E:8329
Elimina 0s: FE80:0:0:0:202:B3FF:FE1E:8329
Campos vacíos: FE80::202:B3FF:FE1E:8329
## Tipos
Los tipos de IPv6 son especificados en el RFC 2373, habiendo tres tipos de direcciones:
- Unicast, identifica una interfaz de un nodo v6.
	- Global, (2000::/3)
	- Link-local, (FE80::/10) utilizadas en el enlace local y limitadas a solo uno.
	- Local única, (FC00::/7-FDFF::/7) direccionamiento dentro de un sitio.
- Multicast, identifica un grupo de interfaces de un nodo (sustituto del broadcast) con prefij FFxx/8.
- Anycast, identifica múltiples interfaces en múltiples nodos, enviando a solo una de ellas, tipicamente la más cercana.
- Loopback, (::1/128) y dirección sin especificar (::/128).

Las direcciones IPv6 se asignan a interfaces de al menos una unicast.
# DNS e ICMPv6
La DNS requiere modificaciones especificadas en RFC 1886.
La ICMPv6 se define en RFC 4443 con nuevas funciones para IGMP adición de NDP y mejora de ARP.
La autoconfiguración tiene dos mecanismos:
- SLAAC
- DHCPv6

# Transición V4 a V6
Se han definido tes principales técnicas de transición en RFC 2893:
- Pila dual, soporte dual de ambas versiones.
- Tunneling, trafico V6 sobre infraestructura V4.
- NAT, traducción de V4 a V6 y viceversa.

# Tags
#2- 
#2-2 
#red 