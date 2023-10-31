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
ettercap -T -q -i ens33 -M arp:remote //10.11.48.142/ //10.11.48.1/ -w bisbi.pcap
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

//nuestro compañero busca cosas

//en otra maquina
scp lsi@10.11.48.143:/home/lsi/tcp_bisbi.pcap .
```
Abrimos en wireshark buscamos el png y en File -> Export object lo guardamos y luego abrimos.
# C)
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
# F) 
Editar en ettercap el valor de remote browser:
```
// /etc/etter.conf
remote_browser = w3m .....
```
Lanzamiento del spofing sobre la maquina con el remote.
```shell
ettercap -T -i ens33 -P remote_browser -q -M arp:remote //10.11.48.142/ //10.11.48.1/
```
# G) x
Generación de peiloads y envió al atacado, la segunda parte es ingeniería social para que parezca natural.
Para creación:
- metasploit + msfvenom (neterpreter/shell/bash)
Social:
- filto ettercap
- ingeniería social

# H)x
MITM ipv6 ettercap + ndp
```
ettercap -T -i 6to4 -Q -M ndp:remote //2002:a0b:308e::1/ //2002:a0b:308e::1/
```
# I)x
arpon(defensa) vs ettercap + arp poisoning(ataque)
- registros del ataque
- mostrar que el arp se mantiene

cong in /etc/arpon.conf
logs in /var/log/arpon.log

Ver el arp:
```
arp
```
Flush arp:
```
ip -s -s neigh flush all
```
Activate arpON:
```
arpon -d -i ens33 -H
```
# J)x
- host dicovery
- port scaning
- os fingerprinting

# K)x
conexiones y ancho de banda consumido
- iftop
- tcptrack
- nethogs

```shell
iftop -i ens33
--
tcptrack -i ens33
--
nethogs
```
# M)x
Diferencia teórica entre DOS directo y reflexivo, como hacerlo con packit (**NIVEL TEÓRICO NO PRACTICO**)

Los Dos directos se basan en esclavizar equipos par inundar de peticiones directas a un servicio, por otra parte el reflexivo se centra en enviar peticiones a servidores de alta capacidad con origen el destino para inundarlo de las replays.
Para realizar estos ataques con packit usaríamos su modo de inyección, para el directo (DDOS) enviando al objetivo directamente
# N)x
ataque DOS web
- victima -> server apache
- atacante
	- sloworis
	- slowhttprest

# O)x
defender apache
- modsecurity (dentro de apache)
- modevaise -0,25 (NO USAR)

# P)x
Averiguar de la usc
- server dns/transferencia de zona
- gestores de contenido
- servidor de correo/estafetas

# Q)x
password guesing
- medusa
- hydra

Se necesita un fichero de users y uno de contraseñas:
- un usuario lsi.
- diez contraseñas siendo la ultima la correcta.

# R)x
Detención de pasword guesing:
- OSSEC

# S)x
OSSEC (IPS)
-  info 
- funcionamiento
- baneo y debaneo de ips (mediante osec conf)

# T)x
| servicio      | versión | puerto |
| ------------- | ------- | ------ |
| Prometeus     | 2.47    | 9000   |
| Node_explorer | -       | 9010   | 
| Grafana       | 10.2.0  | 3000   |

Grafana:
- dashbord 1860

//Prestar atención a como se generan los servicios en los tutoriales.