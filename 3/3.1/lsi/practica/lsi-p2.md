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
Lanzamiento del spofing sobre la maquina con el remote.
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

# H)x
MITM ipv6 ettercap + ndp
```
ettercap -T -i 6to4 -Q -M ndp:remote //2002:a0b:308e::1/ //2002:a0b:308e::1/
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
# J)x k
- host dicovery
- port scaning
- os fingerprinting

```shell
nmap -A 10.11.48.142

Starting Nmap 7.93 ( https://nmap.org ) at 2023-11-07 04:11 CET
Nmap scan report for 10.11.48.142
Host is up (0.00037s latency).
Not shown: 995 closed tcp ports (reset)
PORT     STATE SERVICE    VERSION
22/tcp   open  ssh?
|_ssh-hostkey: ERROR: Script execution failed (use -d to debug)
80/tcp   open  http       Apache httpd 2.4.57 ((Debian))
|_http-title: 403 Forbidden
|_http-server-header: Apache/2.4.57 (Debian)
3000/tcp open  ppp?
| fingerprint-strings:
|   FourOhFourRequest:
|     HTTP/1.0 302 Found
|     Cache-Control: no-store
|     Content-Type: text/html; charset=utf-8
|     Location: /login
|     Set-Cookie: redirect_to=%2Fnice%2520ports%252C%2FTri%256Eity.txt%252ebak; Path=/; HttpOnly; SameSite=Lax
|     X-Content-Type-Options: nosniff
|     X-Frame-Options: deny
|     X-Xss-Protection: 1; mode=block
|     Date: Mon, 06 Nov 2023 16:42:01 GMT
|     Content-Length: 29
|     href="/login">Found</a>.
|   GenericLines, Help, Kerberos, RTSPRequest, SSLSessionReq, TLSSessionReq, TerminalServerCookie:
|     HTTP/1.1 400 Bad Request
|     Content-Type: text/plain; charset=utf-8
|     Connection: close
|     Request
|   GetRequest:
|     HTTP/1.0 302 Found
|     Cache-Control: no-store
|     Content-Type: text/html; charset=utf-8
|     Location: /login
|     X-Content-Type-Options: nosniff
|     X-Frame-Options: deny
|     X-Xss-Protection: 1; mode=block
|     Date: Mon, 06 Nov 2023 16:41:31 GMT
|     Content-Length: 29
|     href="/login">Found</a>.
|   HTTPOptions:
|     HTTP/1.0 302 Found
|     Cache-Control: no-store
|     Location: /login
|     X-Content-Type-Options: nosniff
|     X-Frame-Options: deny
|     X-Xss-Protection: 1; mode=block
|     Date: Mon, 06 Nov 2023 16:41:36 GMT
|_    Content-Length: 0
9090/tcp open  http       Golang net/http server (Go-IPFS json-rpc or InfluxDB API)
| http-title: Prometheus Time Series Collection and Processing Server
|_Requested resource was /graph
9100/tcp open  jetdirect?
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port3000-TCP:V=7.93%I=7%D=11/7%Time=6549AAFD%P=x86_64-pc-linux-gnu%r(Ge
SF:nericLines,67,"HTTP/1\.1\x20400\x20Bad\x20Request\r\nContent-Type:\x20t
SF:ext/plain;\x20charset=utf-8\r\nConnection:\x20close\r\n\r\n400\x20Bad\x
SF:20Request")%r(GetRequest,118,"HTTP/1\.0\x20302\x20Found\r\nCache-Contro
SF:l:\x20no-store\r\nContent-Type:\x20text/html;\x20charset=utf-8\r\nLocat
SF:ion:\x20/login\r\nX-Content-Type-Options:\x20nosniff\r\nX-Frame-Options
SF::\x20deny\r\nX-Xss-Protection:\x201;\x20mode=block\r\nDate:\x20Mon,\x20
SF:06\x20Nov\x202023\x2016:41:31\x20GMT\r\nContent-Length:\x2029\r\n\r\n<a
SF:\x20href=\"/login\">Found</a>\.\n\n")%r(Help,67,"HTTP/1\.1\x20400\x20Ba
SF:d\x20Request\r\nContent-Type:\x20text/plain;\x20charset=utf-8\r\nConnec
SF:tion:\x20close\r\n\r\n400\x20Bad\x20Request")%r(HTTPOptions,D2,"HTTP/1\
SF:.0\x20302\x20Found\r\nCache-Control:\x20no-store\r\nLocation:\x20/login
SF:\r\nX-Content-Type-Options:\x20nosniff\r\nX-Frame-Options:\x20deny\r\nX
SF:-Xss-Protection:\x201;\x20mode=block\r\nDate:\x20Mon,\x2006\x20Nov\x202
SF:023\x2016:41:36\x20GMT\r\nContent-Length:\x200\r\n\r\n")%r(RTSPRequest,
SF:67,"HTTP/1\.1\x20400\x20Bad\x20Request\r\nContent-Type:\x20text/plain;\
SF:x20charset=utf-8\r\nConnection:\x20close\r\n\r\n400\x20Bad\x20Request")
SF:%r(SSLSessionReq,67,"HTTP/1\.1\x20400\x20Bad\x20Request\r\nContent-Type
SF::\x20text/plain;\x20charset=utf-8\r\nConnection:\x20close\r\n\r\n400\x2
SF:0Bad\x20Request")%r(TerminalServerCookie,67,"HTTP/1\.1\x20400\x20Bad\x2
SF:0Request\r\nContent-Type:\x20text/plain;\x20charset=utf-8\r\nConnection
SF::\x20close\r\n\r\n400\x20Bad\x20Request")%r(TLSSessionReq,67,"HTTP/1\.1
SF:\x20400\x20Bad\x20Request\r\nContent-Type:\x20text/plain;\x20charset=ut
SF:f-8\r\nConnection:\x20close\r\n\r\n400\x20Bad\x20Request")%r(Kerberos,6
SF:7,"HTTP/1\.1\x20400\x20Bad\x20Request\r\nContent-Type:\x20text/plain;\x
SF:20charset=utf-8\r\nConnection:\x20close\r\n\r\n400\x20Bad\x20Request")%
SF:r(FourOhFourRequest,182,"HTTP/1\.0\x20302\x20Found\r\nCache-Control:\x2
SF:0no-store\r\nContent-Type:\x20text/html;\x20charset=utf-8\r\nLocation:\
SF:x20/login\r\nSet-Cookie:\x20redirect_to=%2Fnice%2520ports%252C%2FTri%25
SF:6Eity\.txt%252ebak;\x20Path=/;\x20HttpOnly;\x20SameSite=Lax\r\nX-Conten
SF:t-Type-Options:\x20nosniff\r\nX-Frame-Options:\x20deny\r\nX-Xss-Protect
SF:ion:\x201;\x20mode=block\r\nDate:\x20Mon,\x2006\x20Nov\x202023\x2016:42
SF::01\x20GMT\r\nContent-Length:\x2029\r\n\r\n<a\x20href=\"/login\">Found<
SF:/a>\.\n\n");
MAC Address: 00:50:56:97:C7:42 (VMware)
Device type: general purpose
Running: Linux 4.X|5.X
OS CPE: cpe:/o:linux:linux_kernel:4 cpe:/o:linux:linux_kernel:5
OS details: Linux 4.15 - 5.6
Network Distance: 1 hop

TRACEROUTE
HOP RTT     ADDRESS
1   0.37 ms 10.11.48.142

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 190.12 seconds
```
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
# N)x k
ataque DOS web
- victima -> server apache
- atacante
	- sloworis
	- slowhttprest

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

# R)x B
password guesing
- medusa
- hydra

Se necesita un fichero de users y uno de contraseñas:
- un usuario lsi.
- diez contraseñas siendo la ultima la correcta.

# S)x k
Detención de pasword guesing:
- OSSEC

# T)x k
OSSEC (IPS)
-  info 
- funcionamiento
- baneo y debaneo de ips (mediante osec conf)

