# DNS
## Introducción
Las DNS usan como método principal UDP y TCP puntualmente (puerto 53).
Antes del empleo del DNS se hace uso del **fichero de host**, fichero donde se guardan las correspondencias en cada dispositivo de la red.
## Cliente
El cliente es el que se comunica con los servidores DNS en nuestro nombre, enviando una consulta al server DNS y reportando la respuesta al solicitante.
## Servidor
Cada red tiene un DNS, un DNS recibe peticiones que debe resolver de dos maneras posibles (base de datos distribuida):
- Resolución, si se tiene la respuesta se envía directamente.
- Redirección, si no se tiene se redirige la pregunta a un DNS superior.
## Espacio de nombres

![[Pasted image 20230228135520.png]]

### Top-Level Domains (TLDs)
- ccTLDs: dominios de país.
- gTLDs: genéricos
	- genéricos
	- genéricos-restringidos
	- sponsored
- IDN ccTLDs: internacionales.
## Servidores de nombres
Los niveles de dominio tiene DNS para cada nivel de la jerarquía, con los siguientes tipos de servidores:
- Raíz, son servidores con muchas duplicidades que dirigen el tráfico a servidores más concretos. Estas duplicidades comparten la misma IP y al que llegamos es decidido por los routers intermedios. Conocen a todos los TLDs.
- TLD, conocen a los sub-dominios y raíz.
- Inferiores, conocen ips y raíz, si no tienen la IP asociada preguntan al raíz.
## Funcionamiento DNS

![[Pasted image 20230425125725.png]]

Consultas:
- Recursivas
	- DNS hace todo el trabajo para devolver la respuesta.
	- Puede tener múltiples transacciones.
	- No obligatorio.
- Iterativas
	- Si no se tiene la respuesta se devuelve indormación pero n
## Caché
Cada servidor DNS guarda consultas previas, esto hará que las preguntas frecuentes tengan respuesta ya calculada. Estas respuestas no son autoritarias, ya que estas caches no tienen autoridad sobre el dominio.
# Tags
#2-
#2-2 
#red