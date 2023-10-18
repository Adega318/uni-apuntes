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