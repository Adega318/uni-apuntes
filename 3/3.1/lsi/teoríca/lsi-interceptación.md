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
