# Sistemas de almacenamiento
## Modos de transferencia
Tenemos do principales modos de trasferencia de datos:
- Bloque, solicitud de bloques concretos de la memoria, permitiendo un acceso preciso pero obtuso para el uso por usuarios.
- Fichero, solicitudes de ficheros con la recopilación de los bloques que lo componen, permitiendo facilidad de empleo del mismo pero con menor eficiencia.
## Almacenamiento tradicional
El almacenamiento tradicionalmente usado son las cabinas de discos, compuestas de los siguientes componentes:
- Controladora, sistema que procesa las peticiones de bloques.
- Bandeja de discos, chasis que aloja los discos, pudiendo ser:
	- SAS
	- SATA
	- NVMe
Estos componentes dividen el sistema en partes:
- Agregado, conjunto físico de discos.
- Volumen, representación lógica del almacenamiento.
- LUN, conjunto de bloques en un volumen.
```mermaid
flowchart TD
	ci["cluster\ninterconnect"]
	c1[controller 1]
	a1[aggregate 1]
	c2[controller 2]
	a2[aggregate 2]

	ci---c1
	ci---c2
	c1---a1
	c2---a2
```
### Direct attach storage (DAS)
Conexión de manera local usando discos externos, este tipo de conexión tiene una única conexión llevando a cuellos de botella y un gran punto crítico.
### Network attched storage (NAS)
Conexión mediante red TCP/IP para compartiendo la capacidad de almacenamiento, esto ofrece ventajas como:
- Menor coste al usar la red existente.
- Gestión sencilla.
- Menor rendimiento al usar tcp/ip.
- Menor fiabilidad.
### Storage area network (SAN)
Conexión mediante una red específica de almacenamiento, dando gran fiabilidad, disponibilidad y rendimiento.