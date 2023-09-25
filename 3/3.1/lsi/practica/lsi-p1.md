1. arranque
	1. targets
	2. services
	3. units
2. botado
	1. kernel time
	2. userspace time
3. fallo arranque
	1. fallo servicio
4. interfaz ENS34
	1. físico, /etc/network/interface
	```
	auto lo ens33 ens34
	iface lo ...
	iface ens33 ...
	iface ens34 inet static
	```
	2. lógico
5. ruta estática, asignar a los de acceso ens34 un ens33
	1. fichero o comando
6. podado de servicio
	1. seleccionar servicios prescindibles  ( cuidado con las dependencias )
	2. parar servicios con deshabilitar o enmascarar ( deshabilitar lo desactiva pero puede seguir siendo llamado y enmascarar impide por completo su activación )
	3. listar los servicios con arbol de procesos o lista de tiempo
7. script

# C)
Selección del target multi-user.target
```bash
# desactivar lo que no sea multi-user y sus dependencias
systemctrl isolate multi-user.target

systemctl list-units --type=target

# Establecer multi-user como default

systemctl set-default multi-user.target

shutdown -r now


journalctl
```


# D)
Para tratar servicios se usa:
```
sudo systemctl <mask | unmask | disable | enable>
```
Servicios maskeados:
```
e2scrub_reap
cups
cups-browsed
ModemManager
switcheroo-control
bluetoth
accounts-daemon
wpa_supplicant.service
NetworkManager


plymouth
plymouth-start
plymouth-read-write
plymouth-quit
plymouth-quit-wait
speech-dispatcher
avahi-daemon
exim4.service
udisk2
```
Servicios desabilitados:
```
cups
cups-browsed
ModemManager
switcheroo-control
bluetoth
accounts-daemon

NetworkManager
avahi-daemon
man-db
fwupd-refresh.service
exim4.service
udisk2
```

```bash
Edite sobre:
/etc/default/grub

El time out a 0

systemctl disable systemd-timesyncd.service
apt-get install chrony
systemctl enable chrony
```

# A

# B
Versión inicial debian 10, visible con:
```bash
lsb_release -a
```
Actualizado a debian 12, pasando por 11:
```bash
apt update -y
apt upgrade -y
apt dist-upgrade

# Change "buster" to "bullseye"
nano /etc/apt/sources.list

apt update -y
apt upgrade -y
apt dit-upgrade
apt autoremove

# Comprovar versión
cat /etc/os-release

# Change "bullseye" to "bookworm"
nano /etc/apt/sources.list

apt update -y
apt upgrade -y
apt dit-upgrade
apt autoremove

# Comprovar versión
cat /etc/os-release
```
# C
Secuencia de arranque:
```bash
systemd-analyze critical-chain
```
El target actual se puede ver con:
```bash
systemctl get-default
```
Establecer el nuevo target:
```bash
# Desactivar lo que no sea multi-user y sus dependencias
systemctrl isolate multi-user.target

# Establecer multi-user como default
systemctl set-default multi-user.target

#Rinicio para aplicar cambios
shutdown -r now
```
Para ver los servicios instalados:
```bash
systemctl list-unit-files --type=service
```
Para ver otro tipo de unidades:
```bash
systemctl list-units -t help
```
# D
El tiempo de bootup se ve con:
```bash
systemd-analyze

# Para verlo en relación a los servicios
systemd-analyze blame
```
# E
Para ver los servicios fallados:
```bash
systemctl --failed
```
Otros fallos se pueden ver a través de:
```bash
journalctl -b 0 -p 4
```
systemd-timesyncd es un servicio de sincronizacción de tiempo con servidores NTP.
# F
Inicio de ens34:
```
ifconfig ens34

ens34: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.11.50.50  netmask 255.255.254.0  broadcast 10.11.51.255
        inet6 fe80::250:56ff:fe97:cee4  prefixlen 64  scopeid 0x20<link>
        ether 00:50:56:97:ce:e4  txqueuelen 1000  (Ethernet)
        RX packets 6843  bytes 1563475 (1.4 MiB)
        RX errors 0  dropped 2420  overruns 0  frame 0
        TX packets 19  bytes 1426 (1.3 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
        device interrupt 16  base 0x2080  
```
Configuración de ens34:
``
# G
# H
Los principales servicios que eliminaremos:
```
systemctl <mask | unmask | disable | enable>

# Masked
NetworkManager
bluetoth

# Deabilitated
NetworkManager
bluetoth
```
## Bluetoth
```bash
# Autoenable = false
nano /etc/bluetooth/main.conf
```
# I