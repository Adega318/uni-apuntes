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
1. Se aplica la máscara en la IP de destino y se comprueba con la columna de destinos, si se encuentra y las flags son correctas se envía, si hay varias mascaras se selecciona la más larga.
2. Se manda por el default si existe.
3. Se genera error al no poder enviar.
## Tipos de enrutamiento
### Estática
Enrutamiento basado en tablas configuradas a mano, siendo valido para redes reducidas.
### CIDR
Protocolo basado en el enrutamineto de subredes a superedes, consiguiendo enrutar varias direcciones de subred a trabes una o más direcciones de superred.
# Tags
#2- 
#2-2 
#red