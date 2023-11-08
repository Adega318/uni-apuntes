# Sniffing
Proceso de captura de paquetes entre dos equipos.
## Trafico
El sniffing se puede hacer sobre trafico seguro o no seguro, el trafico seguro esta encriptado dificultando la obtención de la información.
# Subnetting
División de redes en redes más pequeñas.
## VLan
Sistema que permite el subnetting de manera independiente del sistema físico mediante el protocolo vlan, este protocolo establece puertos como trunk port que permiten propagar paquetes por la vlan.
Los protocolos de vlan se pueden atacar con herramientas como **Yersinia (capa 2)**.
### Protocolos
Los principales protocolos atacables por Yersinia son:
- STP, convierte la estructura de la red en un árbol usándolo para el trafico de la red evitando los bucles (hace uso de BPDUs).
- OTP
### Switch spoofing
Enmascarado como switch del equipo mediante el uso de Yersinia dando acceso a la capa 2, evitando la mayoría de firewals y vlan.
La protección para este tipo de ataques es el filtrado de las tramas no procedentes de maquinas aceptadas.
### Double tagging
Ataque mediante el doble etiquetado de tramas en vlan.
# ARP Spoofing
# ICMP redirects
Se configura en /etc/systcl.conf con flags para restringir el redirect.
# Source routing
Designación de la ruta de los paquetes en el equipo origen.
# DHCP spoofing
Spoofing de la comunicación con el dhcp, siendo protegido por el dhcp snoping.
## Dhcp snoping
Configuración del dhcp a nivel de conmutador.
# Port stealing
Abuso del sistema dinámico de puertos mediante el envío de paquetes con destino la mac de otro puerto para que el sistema dinámico pase a enviar al nuevo puerto la paquetería, produciendo snifing.
# DNSSec
Sistema de segurizado del tráfico dns con autentificación, requiriendo de herramientas adicionales para el cifrado.
# Arp
- arp -a, tabla
- arp -d \<ip\>, elimina una entrada de la tabla
- arp -s \<ip>\<mac\>, setea una ip fija

Configuración de tiempos de limpieza de caché en gc.stable
## Arp tables
Seteo de reglas en capa 2.
## ArpOn
MERDA
## Snort
# Fluding
Interrupción de los servicios de un conmutador mediante el exceso de fluding.
## Unicast fluding protection
Vigilancia de la tasa de fluding para en caso de actividad anómala reducir recursos.
# Port span and mirror
El port span y miror replican el tráfico de un puerto y lo securiza. Causa problemas por cuello de botella a excepción de que se haga uso de un trunk port.
## Mirror
| Mode | Balans        |
| ---- | ------------- |
| 0    | Roiund roning |
| 1    | Active backup |
| 2    | B. XOR        |
| 3    | Broadcast     |
| 4    | 802.3ad       |
| 5    | Balance TLB   |
| 6    | Balance ALB   |

Para mortar un bounding en una marina hacemos uso de ...
# Firewall
Centrándonos en los firewalls de nueva generación, debemos destacar:
- Trabajo en todas las capas.
- Sistemas de prevención de intrusiones.
- Vinculación con los sistemas de autentificación.
- Análisis de tráfico (problemas con el tráfico cifrado).
# SOC
El soc (centro de operaciones de una organización), compuesto de:
- SIEM, sistema que recopila y procesa los logs de la organización.
- EDR, monitorea las máquinas finales usando agentes (OSSEC).
- NOR
# HSTS
Sistema de seguridad con el cual con la primera conesión con un servidor se envia una cadena con fecha de expiración que asegura el corre