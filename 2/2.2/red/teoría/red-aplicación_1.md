
![[Pasted image 20230424172951.png]]

# HTTP
## Formato
### Petición
Formato:
- Línea de petición, método + URL + versión
- Líneas de cabecera
- Línea en blanco 
- Cuerpo de entidad

### Respuesta
Formato:
- Línea de estado, versión + [código de estado](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)
- Líneas de cabecera
- Línea en blanco
- Cuerpo de entidad

### Cabeceras
- Date: fecha y hora en la que se creó y envió la respuesta HTTP.  
- Server: especifica el tipo de servidor Web que ha atendido a la petición.  
- Last-Modified: indica la fecha y hora en que el objeto fue creado o modificado por última vez.
- Content-Length: indica el número de bytes del objeto enviado.
- Content-Type: indica el tipo de objeto incluido en el cuerpo de entidad, con formato tipo/subtipo.
	- La extensión del archivo no especifica (formalmente) el tipo de objeto.

## Conexión persistente
Tenemos dos modelos de conexión persistente:
- sin pipeline, el cliente hace una petición tras recibir una respuesta.
- pipeline, el cliente hace una petición al encontrar una referencia al objeto.

![[Pasted image 20230424173312.png]]

## Http 2
- multiplexación local
- formato binario
- compresión de cadenas
- server push

## Cookies

![[Pasted image 20230424174738.png]]

Información que se guarda para facilitar la navegación y en casos indeseados seguimiento.
## GET condicional
Get donde se manda el último get sobre el documento, si no se ha modificado no se manda la información.
# SMTP
Protocolo de correo electrónico, pensado para intercambio de mensajes de correo, teniendo como estándar el puerto 25.
Funciona mediante una sincronización seguida del envío de un mensaje, el mensaje debe de ser ASCII, estando los mensajes codificados en [[#MIME|MIME]].
Formato:
- Cabecera, información del correo
	- From
	- To
	- Cc
	- Bcc
	- Subject
	- Date
	- Message-Id
	- Recived
	- Replay-To
- Cuerpo, información en ASCII

## MIME
Método de codificación en ASCII para el envió de mensajes usando SMTP.
# Tags
#2- 
#2-2 
#red