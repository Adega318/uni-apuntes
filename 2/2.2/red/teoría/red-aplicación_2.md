# DNS
## Introducción
Las DNS usan como método principal UDP y TCP puntualmente (puerto 53).
Antes del empleo del DNS se hace uso del **fichero de host**, fichero donde se guardan las correspondencias en cada dispositivo de la red.
## Cliente
El cliente es el que se comunica con los servidores DNS en nuestro nombre, enviando una consulta al server DNS y reportando la respuesta al solicitante.
## Servidor
Cada red tiene un DNS, ningún DNS tiene todas las respuestas si no que redirigen las preguntas a otros DNS que la pueden tener.
## Espacio de nombres
![[Pasted image 20230228135520.png]]
### TLDs
ccTLDs: dominios de país.
gTLDs: genéricos, con tres tipos: genéricos, restringidos y sponsored.
IDN ccTLDs: internacionales.
## Servidores de nombres
- Raíz, son servidores con muchas duplicidades que dirigen el tráfico a servidores más concretos. Estas duplicidades comparten la misma IP y al que llegamos es decidido por los routers intermedios. Conocen a todos los TLDs
- TLD, conocen a los sub-dominios y raíz.
- Inferiores, conocen ips y raíz, si no tienen la IP asociada preguntan al raíz.
## Caché
Cada servidor DNS guarda consultas previas, esto hará que las preguntas frecuentes tengan respuesta ya calculada. Estas respuestas no son autoritarias, ya que estas caches no tienen autoridad sobre el dominio.
# Tags
#2-
#2-2 
#red