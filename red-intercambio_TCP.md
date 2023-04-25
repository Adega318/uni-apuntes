# Protocolo ARQ

![[Pasted image 20230425182513.png]]

Protocolo de parada y espera donde el emisor no emite hasta confirmar la recepción. Esto causa que la velocidad de conexión sea baja, para evitar el problema se mandan paquetes en cadena en lugar de manera individual, necesitando un buffer adecuado para el tamaño de cadena.
## Retroceder N
Trasmisión de paquetes, pudiendo llegar a N paquetes en espera de confirmación, en caso de no recivir ACK reenvia los paquetes en espera. El receptor no requiere de buffer y se establece un número finito de paquete circular.
## Repetición selectiva
Es el retroceder N con ACK individuales.
# Intercambio TCP

![[Pasted image 20230425183751.png]]

Existen dos tipos de trafico de datos en TCP:
- Interactivo, gran numero de segmentos de pequeño tamaño.
- No interactivo, segmentos de grantamaño siendo normalmente el máximo de la red.

# Tags
#2- 
#2-2 
#red 