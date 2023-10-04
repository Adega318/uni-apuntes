# Discovery
## Host
Se intenta descubrir una maquina.
## Port
Se intenta descubrir los puertos de la maquina.
## Fingerprinting
Descubrir características de las maquinas descubiertas.
- activo
- pasivo
## Footprinting

## Google dorks
Búsqueda sobre google mediante scriping para obtener información.

# Fases de la recopilación
1. Fuentes publicas
	1. Maltego
	2. OSINT
	3. Estatales
		1. NIC
		2. RIPE, redes europeas
		3. NCC, entro de coordinación europeo
2. Ip de maquinas
	1. ping, puede ser filtrado por routers.
	2. tracerute, da las ips de la ruta entre dos maquinas pero puede sufrir filtrado.
	3. Bases de datos, información de ips publica.
	4. DNS, buscar en el dns las ip-nombre.
		1. nslookup
		2. dig
		3. ls, trasferencia de zona (usualmente prohibida).
			1. dnsrecom, se hace la resolución por prueba y error (puede no estar permitida la reversa).
		4. Cache snooping, sirve para ver si una maquina concreta ha sido accedida ya por una maquina bajo la dns. Esto se realiza haciendo preguntas sin el modo recursivo activado, que puede estar bloqueado por lo que se puede hacer uso de tiempos de respuesta para estimar si esta cacheado.
3. Puertos
4. Fingerprinting SC
5. ""

Si hay un IPS algunos comandos pueden llevar a problemas.

# Búsqueda de vulnerabilidades
En la búsqueda de vulnerabilidades se puede hacer uso de herramientas de diagnostico automático como:
- openvas
- nessus

Por otra parte existen otras herramientas de manera manual como los CVE y NVD, que dependen del conocimiento sobre la maquina.
# Explotación
Para la explotación existen herramientas como :
- metaexploit
- theFATRAT, creación de troyanos.
- Cobal Strike
- SHODAN, base de datos de exploits y fingerprinting.

## Payloads
- single
- stagers

SET, herramienta de ingeniería social pensada para la automatización de la misma.
## Capa 7
Capa de aplicación de redes.
- WAF, firewal orientado hacia la capa 7 para filtrar el trafico http.
	- modsecurity
	- Infoguat

## Ofuscación
Intento de evitar la detección de los peyloads por parte de las defensas.
- msfvenom
	- msfpayload, creador de payloads.
	- msfencode, ofuscador de payloads.
## Idel Scan
Escaneo de puertos de una maquina usando TCP y una maquina zombi como intermediario. Esto se puede ser evitado a través de un firewall de control de estado.

# OWASP
1. Permisos!!!!
2. Errores de cryptografia
	1. malas implementaciones
3. Injection, problemas ocasionados por mala validación.
	1. sql
	2. ldap
	3. os
4. Diseños inseguros
5. Sec misconfiguration
	1. errores de configuración de seguridad.