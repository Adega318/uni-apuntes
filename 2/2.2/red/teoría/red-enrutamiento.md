# Tabla de enrutamiento
Tabla con la información necesaria para el enrutamiento de paquetes en la red, cada entrada tiene la siguiente información:
- IP destino, host o IP.
- Gateway, IP del siguiente router.
- Mascara de subred.
- Flags
	- U, indica la actividad de la entrada.
	- H, IP de destino es un host.
	- G, necesidad de pasar por router para llegar al destino.
## Algoritmo de enrutamiento
Algoritmo dedicado a seleccionar la entrada de la tabla correspondiente a la IP de destino de un paquete, con las siguientes fases:
1. Se aplica la máscara en la IP de destino y se comprueba con la columna de destinos, si se encuentra y las flags 
# Tags
#2- 
#2-2 
#red