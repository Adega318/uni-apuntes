# Ethernet
Protocolo de acceso aleatorio para canales de difusión, teniendo a través de los años esta evolución:
- Coaxial, conexión de todos los nodos al mismo bus.
- Concentradores, dispositivos conectados a un concentrador que hace de distribuidor.
- Conmutadores, mayor velocidad.

## CSMA
Es un método de trasmisión basado en la escucha y espera parara trasmitir, esto lleva a mínimas colisiones, produciéndose únicamente cuando se produce una trasmisión simultanea, requiriendo confirmación.
## CSMA/CD
Esta es una mejora sobre la CSMA, mantiene la escucha durante la trasmisión para detectar colisiones. Cuando una colisión se produce se espera un tiempo aleatorio para reintentar la trasmisión, aumentando el tiempo cada vez que se falla.
## Trama

![[Pasted image 20230507185300.png]]

Las tramas de ethernet tiene los siguientes campos:
- Preámbulo, patrón de sincronización.
- Destino
- Origen
- Tipo, tipo de protocolo utilizado para los datos.
- Datos, máx 1500 bytes.
- Relleno, relleno para asegurar el funcionamiento de la detección de colisiones.
- FCS, código CRC de detección de errores.

# Wifi

![[Pasted image 20230507192943.png]]

Redes con gran movilidad y flexibilidad con la desventajas del ancho de banda, teniendo distintos tipos componentes:
- Infraestructura, red física que da acceso a internet a la red inalámbrica.
- Punto de acceso, punto donde se pasa de la inalambrica a la fisica
- Medio inalámbrico.
- Equipo inalámbrico.
## Asociación
## CSMA/CA
## Seguridad
# Tags
#2- 
#2-2 
#red 