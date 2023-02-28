# DNS
## Introducción
Las dns usan como método principal UDP y TCP puntualmente (puerto 53).
Antes del empleo del dns se hizo uso del **fichero de host**, fichero donde se guardan las correspondencias en cada dispositivo de la red.
## Cliente
El cliente es el que se comunica con los servidores dns en nuestro nombre.
## Servidor
Cada red tiene un dns, ningundns tiene todas las respuestas si no que redirigen las preguntas a otros dns que la pueden tener.
## Espacio de nombres
![[Pasted image 20230228135520.png]]
### TLDs
ccTLDs: dominios de país.
gTLDs: genéricos, con tres tipos: genéricos, restringidos y sponsored.
IDN ccTLDs: internacionales.
## Servidores de nombres
- Raíz, son servidores con muchas duplicidades que dirigen el tráfico a servidores más concretos. Estas duplicidades comparten la misma ip y al que llegamos es decidido por los routers intermedios. Conocen a todos los TLDs
- TLD, conocen a los sub-dominios y raíz.
- Inferiores, conocen ips y raíz, si no tienen la ip asociada preguntan al raíz.
## Caché

# Tags
#2-
#2-2 
#red