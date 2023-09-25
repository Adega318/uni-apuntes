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
Versión debian 10, visible con:
```bash
lsb_release -a
```
# C
# D
# E
# F
# G
# H
# I