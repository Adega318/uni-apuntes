# DNS
## Introducción
Las DNS usan como método principal UDP y TCP puntualmente (puerto 53).
Antes del empleo del DNS se hace uso del **fichero de host**, fichero donde se guardan las correspondencias en cada dispositivo de la red.
## Cliente
El cliente es el que se comunica con los servidores DNS en nuestro nombre, enviando una consulta al server DNS y reportando la respuesta al solicitante.
## Servidor
Cada red tiene un DNS, un DNS recibe peticiones que debe resolver de dos maneras posibles (base de datos distribuida):
- Resolución, si se tiene la respuesta, se envía directamente.
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
- TLD, conocen a los subdominios y raíz.
- Inferiores, conocen ips y raíz, si no tienen la IP asociada preguntan al raíz.

## Funcionamiento DNS

![[Pasted image 20230425125725.png]]

Consultas:
- Recursivas
	- DNS hace todo el trabajo para devolver la respuesta.
	- Puede tener múltiples transacciones.
	- No obligatorio.
	- Mi DNS suele ser recursiva.
- Iterativas
	- Si no se tiene la respuesta se devuelve información, pero no se hace más trabajo.
	- Servers Raíz y TLD son interactivos.

## Caché
Cada servidor DNS guarda consultas previas, esto hará que las preguntas frecuentes tengan respuesta ya calculada. Estas respuestas no son autoritativas, ya que estas caches no tienen autoridad sobre el dominio.
- Respuestas autoritativa, respuesta hecha por el DNS que conoce directamente la información del servidor buscado.

## Forwarding
Servidores no responsables de ninguna información, solamente destinados a la redirección mediante consultas recursivas y respuestas rápidas mediante caché.
## Consultas
Tenemos cuatro tipos de consultas:
- A (estándar), Nombre -> IP.
- CNAME, búsqueda basándose en un alias.
- PTR, consulta inversa IP -> Nombre.
- MX, consultas DNS para correo.

## Comandos
- nslookup | dig, peticiones al DNS por defecto.
- bind, peticiones al DNS "Berkeley Internet Name Domain".

# P2P
Este modelo se basa parejas que hacen las funciones de cliente y servidor simultáneamente, creando una red con los equipos de usuarios, dando una expansión de la base de usuarios como mejora al servicio y gran tolerancia a fallos, pero baja seguridad y caro en ancho de banda.
Teniendo dos tipos:
- Estructurado, los nodos se organizan de manera concreta.
- Des-estructurado, se conectan de manera aleatoria.
	- Puro, todos los nodos son iguales.
	- Centralizado, nodos centrales que sirven como servidor de directorio.
	- Híbrido, supernodos que realizan ciertas tareas de server directorio.

# Tags
#2-
#2-2 
#red