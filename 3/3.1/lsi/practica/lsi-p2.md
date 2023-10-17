# A)
Install ettercap
```
apt install ettercap-text-only
```
Funcionamiento:
```
ettercap [options][target1][target2]

ejemplo:
ettercap /10.11.48.56//
```
Con ettercap realizaremos ARP spoofing
# B)
Captura de trafico, usando ettercap + wireshark para snifear y visualizar data (pdf, gif, ...)
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