# Discovery

## Host

Se intenta descubrir una maquina.

## Port

Se intenta descubrir los puertos de la maquina.

## Fingerprinting

Descubrir características de las maquinas descubiertas.

- activo

- pasivo
  
  ## Footprinting

## Google dorks

Búsqueda sobre google mediante scriping para obtener información.

# Fases de la recopilación

1. Fuentes publicas
   1. Maltego
   2. OSINT
   3. Estatales
      1. NIC
      2. RIPE, redes europeas
      3. NCC, entro de coordinación europeo
2. Ip de maquinas
   1. ping, puede ser filtrado por routers.
   2. tracerute, da las ips de la ruta entre dos maquinas pero puede sufrir filtrado.
   3. Bases de datos, información de ips publica.
   4. DNS, buscar en el dns las ip-nombre.
      1. nslookup
      2. dig
      3. ls, trasferencia de zona (usualmente prohibida).
         1. dnsrecom, se hace la resolución por prueba y error (puede no estar permitida la reversa).
      4. Cache snooping, sirve para ver si una maquina concreta ha sido accedida ya por una maquina bajo la dns. Esto se realiza haciendo preguntas sin el modo recursivo activado, que puede estar bloqueado por lo que se puede hacer uso de tiempos de respuesta para estimar si esta cacheado.
3. Puertos
4. Fingerprinting SC
5. ""

Si hay un IPS algunos comandos pueden llevar a problemas.

# Búsqueda de vulnerabilidades

En la búsqueda de vulnerabilidades se puede hacer uso de herramientas de diagnostico automático como:

- openvas
- nessus

Por otra parte existen otras herramientas de manera manual como los CVE y NVD, que dependen del conocimiento sobre la maquina.

# Explotación

Para la explotación existen herramientas como :

- metaexploit
- theFATRAT, creación de troyanos.
- Cobal Strike
- SHODAN, base de datos de exploits y fingerprinting.

## Payloads

- single
- stagers

SET, herramienta de ingeniería social pensada para la automatización de la misma.

## Capa 7

Capa de aplicación de redes.

- WAF, firewal orientado hacia la capa 7 para filtrar el trafico http.
  - modsecurity
  - Infoguat

## Ofuscación

Intento de evitar la detección de los peyloads por parte de las defensas.

- msfvenom
  
  - msfpayload, creador de payloads.
  
  - msfencode, ofuscador de payloads.
    
    ## Idel Scan
    
    Escaneo de puertos de una maquina usando TCP y una maquina zombi como intermediario. Esto se puede ser evitado a través de un firewall de control de estado.

# OWASP

1. Permisos!!!!
2. Errores de cryptografia
   1. malas implementaciones
3. Injection, problemas ocasionados por mala validación.
   1. sql
   2. ldap
   3. os
4. Diseños inseguros
5. Sec misconfiguration
   1. errores de configuración de seguridad.
6. haklf
7. Autentificación
8. Integridad de soft y data
9. Monitoreo y logs
10. Secure side request forgery

# Fingerprinting y port scanig

## Gen 1

- Lectura de cabeceras para identificar el sistema del servidor.
- Respuesta por nmaping, comparando las repuestas de la maquina ante un nmap con la esperada por parte del kernel.

## Gen 2

## Gen3

- cmp

## Gen4

Nivel de aplicación

- APLIC, fingerprinting por pruebas de servicio

## Proteción

para la protección se pueden cambiar el comportamiento de la maquina se cambian e /proc/syslmct, a este método se le llama ofuscación, uno de los parámetros mas modificados es el TTL. Los linux suelen tener un TTL de 64 y windows 128.

La ofuscación se puede aplicar también a otros ámbitos como el firewall por las iptables, modificando los MANGLE se puede modificar los paquetes en transito, una de estas modificaciones es el cambio de TTL.

Otro ámbito son las aplicaciones como apache2 donde podemos masquear la naturaleza del mismo a través de la información dada.

- SMTP
  
  - VRFY, petición de verificación de la existencia de un usuario a un servidor de correo
  
  - RCPT TO,
  
  - sea automatiza por stmp

- flags
  
  - nmap
    
    - -sA, ACK que suele ser respondido por un reset indicando que hay un puerto sin filtro (firewal de control de estado)
    
    - -p, puerto
    
    - -sP, host discovery sobre un segmento mediante syng, ack y cmp (importante)
    
    - -6, pruevas sobre la ipv6 que suele estar vulnerable.
    
    - -T 0, intenta evitar la detección como intrusión
    
    - -O xxx.xxx.xxx.xxx, fingerprinting de sistema (importante)
    
    - -sV, fingerprinting de servicio y puertos (importante)

Las respuestas a un port skaning puede retornar:

- open

- closed

- filtered

- unfiltered

- open filtered

- closed



nmap compatible con scripts en lua.



### traceroute

El traceroute busca la ruta entre dos maquinas, los paquetes de traceroute se pueden ver filtrados a menos que se haga uso de las opciones:

- -T

- -V

#### Firewalls

Los fitewalls controlan el trafico que pasa por ellos filtrandolo, dividiéndose en :

- Modo router, integración de firewall en un router con listas de acceso.

- NAT, mejora sobre el router que implementa direccionamiento.

- Transparentes, son firewalls que trabajan exclusivamente en capa 2 evitando cualquier tipo de conexión desde el exterior (puede crearse usando ebtables).

- Nueva generación, firewalls comerciales que implementan las capas de 2 a 7 (caro de carallo).

#### Spider

Recorre el árbol html de servidores dercargandolo, dando puntos donde se pueden probar vulnerabilidades.

#### Crawler

Análisis sintáctico del spidering.

#### Scrapper



#### Hardening

Proceso de reconfiguración para el aumento de la seguridad del un sistema, en linux tenemos herramientas de auditoria como "lynis audit system" que proporciona un reporte de seguridad con recomendaciones de seguridad. Algunas recomendaciones podrian ser:

- libpum-tmpdir

- apt-listbugs

- needvestart

- debsecan

- debsums

- fail2bam, detección de pasword guesing e implementación de respuestas