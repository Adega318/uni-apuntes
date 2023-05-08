# Protocolo ARQ

![[Pasted image 20230425182513.png]]

Protocolo de parada y espera donde el emisor no emite hasta confirmar la recepción. Esto causa que la velocidad de conexión sea baja, para evitar el problema se mandan paquetes en cadena en lugar de manera individual, necesitando un buffer adecuado para el tamaño de cadena.
## Retroceder N
Trasmisión de paquetes, pudiendo llegar a N paquetes en espera de confirmación, en caso de no recibir ACK reenvía los paquetes en espera. El receptor no requiere de buffer y se establece un número finito de paquete circular.
## Repetición selectiva
Es el retroceder N con ACK individuales.
# Intercambio TCP

![[Pasted image 20230425183751.png]]

Existen dos tipos de tráfico de datos en TCP:
- Interactivo, gran número de segmentos de pequeño tamaño.
- No interactivo, segmentos de gran tamaño siendo normalmente el máximo de la red.

El intercambio TCP implementa ARQ retroceso N con matices como:
- paquete fuera de orden son almacenados.
- ignoro de ACK repetidos.
- temporizador de cada grupo de paquetes se mantiene.

## Tráfico
### Interactivo

![[Pasted image 20230425184341.png]]

ACKs retardados:
- No se envía el ACK inmediatamente al recibir el dato, en su lugar se espera para enviarlos con datos.

Algoritmo de Nagle, algoritmo para resolver el problema de numerosos pequeños paquetes convirtiendo TCP en un protocolo de parada y espera.
### No interactivo

![[Pasted image 20230425185148.png]]
![[Pasted image 20230425185245.png]]

Basado en pocos segmentos de gran tamaño, con uso de ventana deslizante para el control de flujo, esto permite confirmar varios paquetes simultáneamente.
## Control de flujo
La ventana deslizante tiene un funcionamiento basado en:
- Ventana ofrecida, número de bytes que el receptor puede soportar (win).
- Ventana utilizable, número de bytes dispuestos para ser enviados.
$$Ventana Utilizable = win-(sig.byte-últimoACK)$$
ACKs acumulativos:
- ACK con un número que es el número enviado en el mensaje al que se responde +1.

### Temp. de persistencia
Tras un tiempo sin tener una ventana ofrecida se lanza un window prober.
- Window probers, segmento de un byte utilizado para comprobar el estado de la ventana.

## Control de congestión

![[Pasted image 20230425210534.png]]

Algoritmo de umbral de inicio lento:
- Debajo del umbral, se aplica una velocidad de envío equivalente a la de recepción.
- Encima del umbral, se aplica un crecimiento suavizado.

## Temporizador Keepalive
Para cuando el extremo del cliente deja de hacer peticiones, se mantiene la conexión por un tiempo bajando los recursos y enviando tras un tiempo un mensaje de confirmación.
# Tags
#2- 
#2-2 
#red 