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
	1. 