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
	2. parar servicios con deshabilitar o enmascarar ( no son lo mismo )
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


journal zt
```
