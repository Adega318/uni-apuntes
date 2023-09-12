nombre: 2.2.3
ip: 10.11.48.143
contraseña
	lsi: 42elratlp
	root: 42elratlp
netmask: 255.255.254.0  /23
gateway: 10.11.48.1
dns: 10.8.12.47 10.8.12.49 10.8.12.50

Configuración:
en el archivo /etc/network/interfares
```
auto lo ens32
iface lo inet loopback
iface ens33 inet
address 10.11.48.143/23
gateway 10.11.48.1
dns-nameservers 10.8.12.47 10.8.12.49 10.8.12.50
```
Reinicio de servicio:
```
/etc/init.d/networking restart
```


