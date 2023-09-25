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
```bash
ifconfig ens34

ens34: flags=4098<BROADCAST,MULTICAST>  mtu 1500
        ether 00:50:56:97:d3:53  txqueuelen 1000  (Ethernet)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 30  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
        device interrupt 16  base 0x2080
```
Configuración de ens34:
```bash
ifconfig ens34 down

# Set maximun packet size
ifconfig ens34 mtu 1200
# Set MAC
ifconfig ens34 hw ether 00:1e:2e:b5:18:07
# Set ip and mask
ifconfig ens34 10.11.50.51 netmask 255.255.254.0

ifconfig ens34 up
ifconfig ens34

ens34: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1200
        inet 10.11.50.51  netmask 255.255.254.0  broadcast 10.11.51.255
        ether 00:1e:2e:b5:18:07  txqueuelen 1000  (Ethernet)
        RX packets 6867  bytes 1568069 (1.4 MiB)
        RX errors 0  dropped 2431  overruns 0  frame 0
        TX packets 19  bytes 1426 (1.3 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
        device interrupt 16  base 0x2080
```
Interfaz lógica:
```bash
# Secondary ip
ifconfig ens34:1 192.168.1.1 netmask 255.255.255.0

ifconfig ens34:1 up
ifconfig

ens34: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1200
        inet 10.11.50.51  netmask 255.255.254.0  broadcast 10.11.51.255
        ether 00:1e:2e:b5:18:07  txqueuelen 1000  (Ethernet)
        RX packets 6898  bytes 1574835 (1.5 MiB)
        RX errors 0  dropped 2444  overruns 0  frame 0
        TX packets 19  bytes 1426 (1.3 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
        device interrupt 16  base 0x2080  

ens34:1: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1200
        inet 192.168.1.1  netmask 255.255.255.0  broadcast 192.168.1.255
        ether 00:1e:2e:b5:18:07  txqueuelen 1000  (Ethernet)
        device interrupt 16  base 0x2080
```
Si estos cambios se realizan sobre **/etc/network/interfaces** son permanentes en reinicio.
# G
Rutas existentes:
```bash
ip route show

default via 10.11.48.1 dev ens33 onlink                                   10.11.48.0/23 dev ens33 proto kernel scope link src 10.11.48.143          169.254.0.0/16 dev ens33 scope link metric 1000  

route

Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
default         _gateway        0.0.0.0         UG    0      0        0 ens33
10.11.48.0      0.0.0.0         255.255.254.0   U     0      0        0 ens33
link-local      0.0.0.0         255.255.0.0     U     1000   0        0 ens33
```
Añadir ruta:
```bash
ip route add 10.11.52.0/24 via 10.11.48.143
```
# H
Los principales servicios que eliminaremos:
```bash
systemctl <mask | unmask | disable | enable>

# Masked
NetworkManager
bluetoth
cups
cups-browsed
ModemManager
switcheroo-control
avahi-daemon
accounts-daemon
wpa-supplicant

# Disabled
NetworkManager
bluetoth
cups
cups-browsed
ModemManager
switcheroo-control
avahi-daemon
accounts-daemon
wpa-supplicant
```
## Bluetoth
```bash
# Autoenable = false
nano /etc/bluetooth/main.conf
```
## Grup
Poner el time_out a cero en **/etc/default/grub**
# I


