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
```mermaid
flowchart TD
	ci["cluster\ninterconnect"]

	subgraph \n
		c1[controller 1]
		a1[aggregate 1]
	end
	subgraph 2
		c2[controller 2]
		a2[aggregate 2]
	end

	c1---ci---c2
	c1---a1-.-c2
	c2---a2-.-c1
```

