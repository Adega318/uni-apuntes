deck:: [[KISS/Uni LSI]]

- Apuntes
	- Siglas a saber
	  collapsed:: true
		- CPE #card
		  id:: 6551196e-a41e-4583-b023-8da1c426beda
			- common platform enumeration
		- OVAL #card
		  id:: 6551196e-cdb5-48ec-8c90-68b0975fe926
			- Open Vulnerability Assesment Language
			- OVAL® 
			  International in scope and free for public use, OVAL is an information 
			  security community effort to standardize how to assess and report upon 
			  the machine state of computer systems. OVAL includes a language to 
			  encode system details, and an assortment of content repositories held 
			  throughout the community.
		- CVSS #card
		  id:: 6551196e-ee6e-4d17-9131-8f74923201a6
			- Common vulnerability score system
		- CWE #card
		  id:: 6551196e-440f-4a9d-8427-b2a1c31aff5b
			- common weakness enumeration
		- DOS #card
		  id:: 6551196e-7fc1-46df-ba16-c48c14010f4b
			- denegation of service
		- LDAP #card
		  id:: 6551196e-33c7-4a73-8780-52af668596a0
			- Lightweight Directory Access Protocol
		- HARD #card
		  id:: 6551196e-4bc1-40f9-81c3-893d4a616831
			-
		- NVD #card
		  id:: 6551196e-b386-492a-8068-7836b601516e
			- National vulnerability database
		- NIST #card
		  id:: 6551196e-95f6-4111-894d-0f2a05a8abb6
			- National intitute of standards and technology
		- Categorias de ataque #card
		  id:: 6551196e-4fe9-4f0a-a328-024fc23486d3
			- interrupcion
			- interceptacion
			- modificacion
			- generacion
		- vectores de ataque, vulnerabilidad
		- amenaza, accion que explota vulnerabilidad
		- *poisoning #card
		  id:: 6551196e-abaf-4a90-8bf9-049c6d6bda75
			- envenenamiento de x
		- injection, injection
		- OSINT #card
		  id:: 65687e66-98e1-4b79-8b66-79269df138eb
			- Information gathering and processing from public information
		- ASVS #card
		  id:: 65687e66-1c19-47c3-b959-ccb583861f5a
			- (Application Security Verification Standard)
		- OWASP #card
		  id:: 65511cdd-a8d1-4475-8622-feb2a1483888
			- Open web application security project
		- PKI #card
		  id:: 656b1823-4b12-4543-aefa-3587f309cdcd
			- Public key infrastructure
	- Ataques
		- Reconocimiento
		  collapsed:: true
			- Tipos de indexadores web #card
			  id:: 65687e66-2d3e-4514-a3f2-b290bec1050a
				- Spider
				- Crawler
				- Scrapper
			- Pasos para el Reconocimiento #card
			  id:: 65687e66-cec7-4f4f-96c1-6635f76f2c79
				- (No hay pasos especificos antes)
				- 4 Puertos
				- 5 Fingerprinting OS
				- 6 Fingerprinting Puertos
				- 7 Mapa
				- 8 Busqueda de vulnerabilidades #card
				  id:: 65687e66-8e09-425e-925a-e3449a808075
					- General
						- Openvas
						- Nessus
					- Web
						- nikto
						- zap
						- w3af
					- CVE
					- NVD
					- Shodan
					- General
						- Inmunity canvas
			- Recognaissance (Reconocimiento, Fingerprinting y port scanning)
				- 1 generation (R. ASCII)
					- Protection : camouflage
					- nc -v -n -w1 x.x.x.x 21-180 => Banners of services
				- 2 generation (R. TCP / IP)
					- Protection : camouflage
				- 3 generation (R. ICMP)
				- 4 generation (R. Application) (Layer 7)
				- Additional
					- lynx -head -dump http://
					- whatweb (fingerprinting web servers)
					- Get headers web
					- SMTP
						- smtp-user-enum -M RCPT -U u.txt -T server.tx
				-
			- nmap #card
			  id:: 65687e66-4e56-437c-99e0-21fe61f196f3
				- -sS -> sync
				- -sA -> ack
				- -sP -> udp
				- -T -> wait between
				- -O -> Operating system
				- -SV -> services
				- -sp -> ports
				- Ports state
					- open
					- closed
					- filtered
					- unfiltered
					- open | filetered
					- closed | filtered
				-
			- Deteccion de routers y firewall #card
			  id:: 65511e30-5cc6-42dc-9ab7-e60550759887
		- Obfuscation #card
		  id:: 65511e1b-40ec-4919-a7d1-9f1be3126e27
		- Explotacion
		  collapsed:: true
			- Tipos de ataques #card
			  id:: 65511dee-862f-4ee5-b21a-230a20c3f462
				- {{cloze Information gathering}} (Descubrir informacion)
				  id:: 28c6fd02-444a-4b44-8de8-b583a070586b
					- Tipos #card
					  id:: 5e0b0953-2435-4a2a-8798-dcc2bc4420af
						- {{cloze Host discovery}}
						  id:: 2d888360-381f-44c3-bc11-101b299431c2
						- {{cloze Port scanning}}
						  id:: a8bb1584-f5b0-4532-ba44-efba67591fe4
						- {{cloze Fingerprinting}}
						  id:: ef45e305-259e-483d-b8f0-25d053ec27af
						- {{cloze Footprinting}}
						  id:: 0cff5ad3-8275-4d28-94de-32c6a6d820ce
						- {{cloze Google hacking / dorks}}
						  id:: c4af3376-7917-4c96-bac1-fc9657f693b4
						- Herramientas
							- Maltego
							- Nethub
				- Ataque de{{cloze Modificacion}} (pueden ser agnosticos)
				  id:: 9b85e625-d1de-47d9-9c48-ebe0a245d881
					- Ataque contra la {{cloze integridad}}
					  id:: ae069cba-25cd-4bb3-a33e-69c920ded057
					- Se protege con funciones :-> {{cloze hash}}
					  id:: 0124673b-bf10-484a-ae9b-1cd45bb4ea64
				- Ataque de {{cloze Generacion o fabricacion}}  (Se requiere conocimiento de secretos)
				  id:: 0fcea17a-f3cb-45a8-a829-85f25fee7695
					- Ataque contra la {{cloze  autenticidad}}
					  id:: bdef890c-ba3b-483c-8290-55819043fe8f
					- Herramientas
						- hping 3
						- scapy
						- packit
			- Explotacion Herramientas #card
			  id:: 2413494e-60be-4c6e-9533-7833b92055a9
				- Metasploit
			- Metasploit resources #card
			  id:: 65687e66-375f-4b49-b80a-42b17e6eaf21
				- Payloads
					- Modulo para trabajar
					- Tipos
						- Single
							- Explotacion de vulnerabilidad
						- Stagers
							- Establecimiento de conexion / abrir comunicaciones
						- Stages
							- Utilidades
							- Meterpreter (ejemplo)
					-
				- SET
					- Social Engineering tool
				- Capa 7
					- WAF #card
					  id:: 65687e66-5cc1-47f3-9bc4-a0ff53713d5c
						- Web Application Firewall
						- Ejemplo
							- modsecurity
							- cloudfare
							- infoguard
						- Attack
							- wofww00f
						-
						-
				- Explotacion
				- Ofuscacion #card
				  id:: 65687e66-459c-49f4-8ce6-e5b3d61d26b6
					- Avoid payload detection by antivirus
					- msfpayload -> msfencode => msfvenom
				- Reconocimiento proteccion #card
				  id:: 65687e66-9430-4948-9234-af7362dbbcdf
					- Port scanning
					- Firewall
						- Domain
							- Layer 2 3 4
						- Types
							- Statefull
							- Stateless
					- Idle scan
						- Escaneo oculto mediante maquina de 3
						- nmap
						- Como funciona el uso de zombie
							- Se comprueba el ip-id de la zombie con sync-ack
							- Spoofea ip contra objetivo
							- Se comprueba si ip-id incremento en 2
				- Tipos de redireccionamiento #card
				  id:: 65687e66-4fc8-4bd9-9bdb-54d6caf86ddb
					- NAT
					- gNAT
			- OWASP
				- Open web application security project
				- Owasp top 10 #card
				  id:: e8948938-09b8-4a3e-89a3-b26d8fb44dad
					- A1 Broken Access control
						- Loss over the user priviledge , mainly to switch user or to admin
						- Path travesal -> Get accessover filesystem files
						- Insecures Ids
						- Wrong permissions
					- A2 Cryptographic failures
						- No / wrong data encryption
					- A3 Injection
						- sql / ldap / os ...
						- XSS cross site scripting
					- A4 Insecure design
					- A5 Security Misconfiguration
						- Bucket AWS
						- HTTP misconfigured
						- error messages
						- Security patches not done / not udating
						- XXE -> XML External Entities
							- Information discovery through validating info on mailicious owned entity
					- A6 Vulnerable outdated components
					- A7 Authentication
					- A8 Soft & data integrity
					- A9 Security loging and monitoring failures
					- A10 Server side request forgery
				- Owasp Top Ten Proactive Controls #card
				  id:: 39acc450-0649-4c53-a375-03601748cb74
					- 1 Define security requirements
					- 2 Use security libraries
					- 3 Secure database access
					- 4 Encode and escape (avoid scripting)
					- 5 Validate info
					- 6 Improve Access control
					- 7 Encrypt everything
					- 8 Logging and monitorization
				- ZAP (analyze vulnerabilities)
		- Ocultacion
		  id:: 65687e66-5319-4d00-b938-db02223cf82f
			- Ips #card
				- \NAT
				- Proxies #card
				  id:: 65687e66-1f63-419c-94e1-70505410fa8c
					- Http
					- Socks
						- Any comm protocol
		- Interceptacion #card
		  id:: 65687e66-5843-4240-950c-9da2cdb405cc
		  collapsed:: true
			- Sniffing
				- Not secure protocol
				- Secure protocol
			- Mirroring
				- to setup a IPS
			- Subnetting
				- Ventajas
					- Rendimiento
					- Ahorro de direccionamiento
				- VLAN
					- Tener la red privada geograficamente distribuida
					- Trunk port
					- Por que
						- Dar logica a redes distribuidas
						- Aplicar politicas de seguridad/gestion de forma generalizada
					- Protocolos
						- DTP
							- Dynamic Trunk Port
						- 802.1q
					- Tipos de ataque
						- Switch spoofing
						- double tagging
					- Herramienta de Ataque Yersinia
						- DTP
						- STP
						- 802.1q
						- DHCP
						- 802.1x
					-
					-
				- STP
					- attacks
						- Become root node
						- MITM
						- Topology change modification
							- Recalculate tree
					- Defenses
						- Root bridge guard
							- Block all non trunk guards from enter the tree
						- BPDU Guard
							- Do not accept BPDU packets from non trunk guards
			- Arp spoofing
			- MITM
			- ICMP Redirect
				- Half Mitm
			- Dhcp spoofing
				- ettercap -Tq -M dhcp
				- counter dhcp snooping
					- Choose dhcp packets on x ports
			- Port stealing
				- ettercap -Tq -M port:
			- Dns spoofing
				- counter dnssec
					- +Dns Over TLS // DNS over HTTPS
			- Simulador GNS3
				- Simulador3
		- Inundacion #card
		  id:: 65687e66-30af-48a0-8435-eea1f7ee3550
		  collapsed:: true
			- Tipos #card
			  id:: 65687e66-d6ae-4cae-b1da-c64c8e94f2b3
				- Reflectivo
					- Unitario
					- Multicast
					- Broadcast
				- SYN Flood
			-
			- Factor de Amplificacion #card
			  id:: 65687e66-b8ea-4e04-aad6-8407b0f3c614
				- Mediante tecnicas multiplicar el numero de paquetes recibidos por el defensor con respecto a lo enviado.
			- Counter #card
			  id:: 65687e66-fdae-4a62-a14d-3e863d9109f7
				- Firewall control de estado
				- TCB (TCp Backlog)
				- TCP Sync cookies
				- Syn cache
					- Tabla Hash
				-
		- Interrupcion
			- DoS/DDoS #card
			  id:: 65687e66-42a0-48ff-896f-6423c0967828
				- Logico
					- Vulnerabilidad
			- Ataques web #card
			  id:: 65687e66-230c-4317-9655-3901a740cb99
				- Slowloris
					- Se envian cabeceras sin retorn de carro para que se quede esperando
				- Slow post
					- indicar que se va a enviar post y hacer que reserve recursos
				- slowread
					- Explotar get
		- Extra
			- Jump firewall
			  collapsed:: true
				- port forwarding
				  collapsed:: true
					- ssh x.x.x.x (origin) -p 443 (port of x.x.x.x) -l user -L 2128(portlocalhost):y.y.y.y:2128(port y.y.y.y)
					  collapsed:: true
						- -L -> -R  reverse
						- -D dinamic forwarding
					- ports opened
					  collapsed:: true
						- localhost
						  collapsed:: true
							- 2128
							- high port
						- x.x.x.x
						  collapsed:: true
							- 443
							- highport
						- y.y.y.y
						  collapsed:: true
							- 2128
					- To access not the 443 but the 2128
				- differences
				  collapsed:: true
					- 127.0.0.1
					  collapsed:: true
						- Only me
					- myprivateip
					  collapsed:: true
						- my lan
					- 0.0.0.0
					  collapsed:: true
						- everyone
			- Portknocking
			  collapsed:: true
				- knockd
				- web knocking
			- LAN switch security (what hackers know about your switch) (Book)
			- Cookies #card
			  id:: 65687e66-ca38-4ea4-a9ac-2eba75bec21e
				- Cookies son limitadas
				- Ataque de cookies #card
				  id:: 65687e66-aefd-4978-a2f4-b96cbbc43526
					- Sidejacking
						- Robo de cookie de autenticacion
				- Tipos
					- Persistentes
					- supercookies
					- zombie-cookies
					- *-cookies
				- Framework
					- evercookie
	- Defensa
	  collapsed:: true
		- Hardening linux
			- lynix audit system
			- install libpam-tmpdir
				- secure scaling privileges
			- sandbox
			- systemd-analyze security x
			- strace -e33
			- How to restart services to get new libraries
				- systemctl restart
					- Restart un servicio
				- systemctl daemon-reload
					- Detectar uno nuevo
				-
		- Protocolos de seguridad de OS (Hardening)
			- PAE (Physical Address entension) #card
			  id:: 65687e65-213e-4439-98cb-1574a722708d
			- DEP (Data execution Prevention) #card
			  id:: 65687e65-2f78-4efb-a1d7-ae86a3595615
			- Limitacion de recursos a usuarios #card
			  id:: 65687e65-4800-416a-893a-95f7bc95f6c1
				- /etc/security/limits.conf
			- PAM (Process authetication module) #card
			  id:: 65687e65-0981-46ea-9eae-6671e9d23522
				- /etc/pam.d/common-password
					- rounds => rehashing
				- chage command #card
				  id:: 65687e65-ffdf-411f-8f6d-19a593ff88e2
					- User-Password change policy
				- Libraries
					- pam-cracklib
					- pam-passwdqc
					- pwquality
			- umask command #card
			  id:: 65687e65-27a0-4c5a-9813-9834aaaaf9ff
				- Default permission file creation
			- Particionado de discos #card
			  id:: 65687e65-7c11-4268-b3c5-b507dfab9819
				- Swapping
				- Efficiency
			- Kernel #card
			  id:: 65687e65-03c6-4085-8aae-0be9f9180f84
				- /proc/sys/kernel
					- modules_disabled
				- /etc/modprobe.d/blacklist.conf
			- USB #card
			  id:: 65687e65-bdb7-40d4-bdf3-7039e41b7177
				- Disable if not used
				- usb-guard kernel module
			- ARP
			- firewall
			-
		- password
			- hash info gathering #card
			  id:: f1796d81-b89e-4011-9323-22600c17b6a0
				- hash identification
				- findmyhash
			- password guessing #card
			  id:: 08c8a4ce-d281-412b-b9ba-8b4589200e57
				- guess password
			- captchas #card
			  id:: 48d7ad41-7839-424a-bc62-28bc6656bb82
				- avoid bots
			- HIPS #card
			  id:: cb805ec7-b8c7-49c3-9b3f-0bffcf949c81
				- (Host Intrusion protection system)
				- OSSEC
				- fail2ban
			- grub protection #card
			  id:: cef3684a-1df7-463d-8fc3-3958af4200a8
				- grub-mkpasswd-pbkdf2
			- tempest #card
			  id:: d3954533-3fe5-4fd0-bf4e-06d11d60fa71
				- electromagnetic attack
			- Rebailing and reflow #card
			  id:: 0a788653-f037-49ad-b959-9b6e5b35f41e
				- Solve hardware tin problems
			- Wifi password attack #card
			  id:: 1d13cd65-9856-4652-ad7c-4737e2ccca47
				- Krack attack
					- get password of wifi through retrying password in a mitm
		- File destroy
			- commands #card
			  id:: 0678ae05-1c23-42a1-815f-5c22fade0a07
				- srm
				- shred
				- wipe
				- dd if=/dev/urandom
				- sfill (wipes free space)
				- sswap (swap)
				- smem (ram)
		- Anonymous nets #card
		  id:: 9781cb51-e25b-4ca7-b855-70c3e030f829
			- TOR
				- torvegas
					- Adjust tcp parameters
				- tornolas
					- Future latency estimation
			- FReenet
			- i2p
			- JAP
			- Retroshare
			- Morphmix
		- How to Proxy #card
		  id:: 65511f06-c702-4bf8-9b62-879a29b3950e
			- In the url htpp://a.com/http://b.com...
		- Interceptacion Counter #card
		  id:: 65511ffa-0ea3-47ba-8f9a-e316d2a06889
			- SNORT (IPS)
			- Unicast flooding protecting
			- DHCP snooping
				- Asign port for dhcp refusing others
			- Port security
			- Test Access Port
			- New generation firewall
			- SIEM (System Information event management)
			- SOC (Security Operational Center)
			- EDR (Endpont detection &1 response)
			- NDR (Network Detection & Response)
			- SORNS (Spam and open relay blocking system)
			- HSTS (HTTP Strict Transport Security)
	- Red
		- Quien asigna rangos de red #card
		  id:: 65687e65-2e4a-44a5-a92b-10a664fcf966
		  collapsed:: true
			- NIC
				- Network information center
			- RIP
				- Redes IP Europeas
			- NCC
				- Network Coordination Center
		- Deteccion de todo tipo de maquinas #card
		  id:: 65687e65-4522-4f4a-ac8a-2d8521a4c479
			- Informacion corporativa
			- Inteligencia
			- Ingenieria social pasiva
		- Ip de maquinas
			- Herramientas de deteccion #card
			  id:: 65687e65-6809-4b84-9e35-a38d569da8b8
				- ping
				- traceroute
		- DNS
			- firewalls basics #card
			  id:: 65687e65-a363-4fed-98b6-9863464084b0
				- iptables
				- nft
			- Tipos de Dns #card
			  id:: 65687e65-207e-4cc9-8a6c-8d5627262696
				- Resolucion directa
				- Resolucion inversa
			- Servidores Dns tipos #card
			  id:: 65687e65-75fe-4e03-9509-e0fe344af9d1
				- Primarios
					- Deben ser mantenidos por el tecnico
				- Secundario
					- Copia de primarios
			- Tipos de Registros DNS #card
			  id:: 65687e65-d096-41e9-887f-e785a4bf44bc
				- A
					- Ipv4
				- AAAA
					- ipv6
				- CNAME
					- Redireccion dominio
				- NS
					- Redireccionamiento a server dns
				- MX
					- Servidor correo electronico
				- Ptr
					- Dns inverso
			- Herramientas
				- dnsenum
				- nslookup
				- dig
				- dnsmap
			- Ataques contra una maquina #card
			  id:: 65687e65-2cfe-4b25-8ea7-089758301bdb
				- Reconocimiento de zona dns
					- Conocer el nombre de las ips en dns
						- nmap -sL 194.112.X.1-254
				- Cache Snooping
					- Ver que paginas han sido visitadas
					- dns recon -t snoop -n x.x.x.serverdns -D file -> comprueba los nombres del file
						- normalmente esto esta deshabilitado pero se puede usar -t para medir tiempo de respuesta
		- firewalls basic tools #card
		  id:: 65511d53-1875-474d-a820-21c57ac4e531
			- iptables
			- nft
		- Tipos  especiales de firewall #card
		  id:: 65687e65-0d31-4302-b558-3dd48c3d165c
			- Control de estado
			- Router (Hace routing)
			- NAT (Hace NAT)
			- Transparentes (inaccesibles a nivel de paqueteria)
		- Port Span/Mirroring
			- Mode #card
			  id:: 70331661-d6e5-45e4-9348-0886ee836068
				- 0 - Round robin
				- 1 - Active Backup
				- 2 - Calanced XOR
					- (Origin MAC XOR Destiny MAC) % n
				- 3 - Broadcast
				- 4 - 802.3ad
				- 5 - Balance tlb (Sending adaptable charge)
				- 6 - Balance alb (Both way adaptable charge)
		- Defensa
			- Defensa #card
			  id:: 656b1809-2d58-489f-99e2-d3e4c1af1d62
				- iptables + plugins
			- QoS #card
			  id:: 629a47e6-cb4b-4d03-83b1-fbec86fcf01d
				- Traffic shaping
				- Packet Shaping
				- Reverse proxy
			- Pruebas de carga #card
			  id:: e30d8209-2f55-4305-be7f-9f002b6db73a
				- j meter
				- apache bench
			- ipv6 #card
			  id:: d27d46a3-ed81-46f2-87b5-5bab671b897e
				- SNDP ->PKI
				- Ataque a NDP -> RA (router advertisement) -> SLAAC (Stateless Address configuration )
	- Inteligencia
	- Curiosidades
		- diferencia medio compartido conmutado  #card
		  id:: 6551196e-160d-4dbf-a908-60c180be6d2f
			- compartido accede a todo y conmutado se balancea
		- Como hacer ARP poisoning en ipv6 #card
		  id:: 65511b07-6119-4b9c-a6e1-b562216f2943
			- No se puede no existe arp en ipv6, en su lugar ndp
		- 802.1q -> #card
		  id:: 65512057-a062-401a-b65d-3e3607bb97c0
			- VLANs