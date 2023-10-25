# NAT
Oculta la ip sustituyendo tú ip por la del NAT, dejando rastro en la NAT (poco discreta). Los scripts pueden pedirte la ip.
# IP/Mac spoofing
Usar las mac e ip de otros equipos para ocultación, vulnerable a detección por la red.
# Proxi
Permiten el envió de información a trabes de otros países para evitar la recuperación de información por parte de autoridades (burocracia), el proxi tiene control sobre toda la información que pasa (peligro).

```note
Honeys, sistemas vunerables intencionalmente con deteción de ataques para obtener información del metodo de ataque
```

Los tipos de proxis son:
- Transparentes, sirven como túnel manteniendo tú información.
- Anónimos, no se introduce tu información.
- Alta disponibilidad, proxys de alta capacidad de carga.
- Ruidosos, introducen ruido en la información personal para anonimato.

# Conexiones ajenas
Reduce la posibilidad de correlación con la persona.
## Crakeo
En el crakeo de wifis tenemos comandos como:
- ng
	- airmon-ng, monitora la wifi.
	- airodump-ng, captura el trafico wifi.
	- airreplay-ng, enviado de paquetes (se puede usar para deautenticar).
	- aircrak-ng, crakeador de hanshakes orientado a WPA2.

El proceso típico es comenzar con un monitoreo del wifi, capturar el trafico obteniendo información de los puntos de acceso en la red, en caso de que halla conectadas maquinas
desautenticaremos a una de las maquinas para que cuando se reconecte, capturando en handshake tras lo cual pasaremos a crakearlo.
### Handshake
El proceso de handshake comienza con un ANonce enviado por el punto de acceso, al cual se responde con un PTK con los siguientes campos:
- PMK, clave codificada
- Anonce, número aleatorio recibido 
- Cnonce, número aleatorio de respuesta.
- MAC PA
- MAC Cliente

El punto de acceso responde con un GTK con el Cnonce y el hash del PTK gracias a este hash que contiene la contraseña se puede recuperar con la ruptura del hash.
### Crakeo de hashes
Para el crakeo de hashes se usan herramientas como hashcat, cain&abel, jhon, ...
Para hacer que los hashes sean únicos se hashean con un numero en base 64 aleatorio (SAL)
#### Dicionarios
Los diccionarios priorizan la búsqueda de contraseñas más probables, para esto tenemos herramientas como:
- cewl, saca términos de webs.
- mutator/crunch, refinamiento de dicionarios.
- hashcat, herramienta de crakeo de hashes altamente potente.

#### Herramientas
- hash-identifier
- hash-id
- findmyhash, busca en una base de datos.
## Password guessing
Ataques que en función a un diccionario prueba las posibles contraseñas para obtener la correcta. Los problemas con la necesidad de tener un diccionario de alta calidad, deja restos en los logs y tarda mucho tiempo.
Para realizar estos ataques tenemos impedimentos como:
- Catcha
- filtros de red
	- ip
	- user

Las principales herramientas para este tipo de ataques son:
- medusa
	- -d, muestra todos los módulos.
	- -M ssh -q, atques en ssh.
	- -h 10.11.48.142, ataque a compañero.
- h-craken
- hydra

Y las herramientas para la defensa son:
- hash-limit, restricciones en los intentos de contraseñas.
- fail2bam, 
- OSSEC, sistema de prevención de intrusiones en host ( HIPS )

## Flushion
Enmascara un punto de acceso.
# Borrado
Para realizar el borrado casi permanente de la información tenemos herramientas como:
- srm
- dd, borra todo un disco duro.
- sfill, borra de forma segura el espacio libre del disco duro.
- sswap, borra de forma segura el swap del dispositivo.
- smenn, borra de forma segura la ram.
- erraser (windows)

# Tor
Para usar la red tor se convierte nuestra paqueteria usando un **tor proxi**, estos paquetes se envían por **tor rutes** compuestas de nodos.
## Cifrado
El sistema de cifrado de cebolla se basa en cifrar el paquete un número de veces igual a los nodos por los que pasara, en cada nodo se quitara una capa de cifrado, en el de salida el paquete quedara limpio y sera enviado al destinatario.
En este proceso los nodos solo conocen el siguiente y anterior nodo en la tor rute.
## Nodos
En tor los nodos se clasifican en:
- Entrada
- Intermedio
- Salida
## .onion
Dominio interno para la red tor donde los servicios están representados por una cadena hexadecimal .onion, siendo accesibles desde la red tor.
## Deepwebp
Toda la web no indexable por los navegadores.
# Port forwarding

# Proteger Grub
grub-mkpasswd-pbkdfz

/etc/grubd/40_custom
set superuser=root
password-plokdfz root