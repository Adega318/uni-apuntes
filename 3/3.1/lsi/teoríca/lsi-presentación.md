# Conceptos
## Seguridad
La seguridad se divide en la seguridad de la información, ámbito de la protección y distribución segura de datos (contiene la seguridad informática), y seguridad informática, serie de protocolos y metodologías para proteger y trasmitir seguramente la información en sistemas informáticos, la segunda esta contenida en la primera.
## Vulnerabilidades
Una vulnerabilidad es una debilidad en un sistema que compromete su seguridad, con respecto a las vulnerabilidades tenemos los siguientes conceptos:
- ***CVE***, lista de todas las vulnerabilidades (no base de datos)).
- ***CVSS***, sistema de puntuare de peligro de las vulnerabilidades.
- ***CWE***, clasificación por características de las vulnerabilidades.
- ***CPE***, definición de las distintas plataformas de trabajo (sistema optativo, ...).
- ***OVAL***, lenguaje de programación orientado a la representación de vulnerabilidades.
- ***NVD***, base de datos con vulnerabilidades y todo lo anterior.
- ***0-day***, vulnerabilidades no conocidas públicamente.

## Explotación
La explotación es el uso de vulnerabilidades, conociendo el método de explotación como exploit, estos exploits son considerados amenazas.
## Ataques
Un ataque es la acción de explotar una amenaza de un sistema, según de el punto de comunicación de ataque a un servicio se categorizan como:
- Interrupción, corta la comunicación del servicio.
	- DOS, ataques que abusan los servicios para inutilizarlo.
	- DDOS, ataques que sobrecargan los servicios.
- Intercepción, lee la comunicación del servicio.
	- Snifing, lectura de la comunicación privada.
- Modificación, modifica la comunicación del servicio.
- Generación, genera comunicación para del servicio.

### Ataques de denegación de servicio
Estos ataque caen bajo la categoría de interrupción que usando gran número de peticiones para sobrecargar el servicio atacado. El método de defensa más comunes con el Trafic shping, se realiza restringiendo el número de conexiones para asegurar la calidad del servicio. Esta solución pude causar problemas con **Proxys** por lo que se debe filtrar los usuarios a los que someter al shaping.
## Sistemas de detección
Los tipos de sistemas de deteción:
- IDS, sistemas que analizan el sistema en busca de ataques.
	- SNORT
	- SURICATA
- IPS, sistema que detecta e intenta prevenir el ataque.
- Sensores,
- Red, sistemas basados en el análisis del transito

# Infraestructuras criticas
Infraestructuras de gran importancia
## Redundancia
