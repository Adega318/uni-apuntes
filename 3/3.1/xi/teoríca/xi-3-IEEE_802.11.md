# Capa MAC
## Problema del nodo oculto y expuesto
En la trasmisión inalámbrica tenemos dos principales problemas por solapación de señales de nodos.
### Nodo oculto
En una red con tres nodos donde dos tiene comunicación a uno y no entre ellos, esto lleva a la solapación de las comunicaciones con el nodo común.
### Nodo expuesto
Un nodo se comunica con otros dos inconexos, este nodo transmite a uno de ellos y el otro nodo inconexo no puede trasmitir a un tercero por la trasmisión del nodo medio pese a no ocasionar colisiones.
## CSMA/CA
La estrategia CSMA/CA se basa en la escucha antes de hablar y evitar colisiones. El proceso de trasmisión con esta estrategia se basa en:
- Trasmitir sin esperar si el canal está libre.
- Si está ocupado esperar un tiempo aleatorio tras la liberación del canal, si se interrumpe esa espera con una trasmisión se pausa la cuenta atrás.
>[!Warning] Esta estrategia no detecta colisiones.
## MACA
Estrategia de evasión de colisiones mediante señalización:
- RTS, solicitud del canal para el envío de señales.
- CTS, respuesta del receptor permitiendo el envío.
Estos paquetes contienen:
- Dirección del emisor.
- Dirección del receptor.
- Tamaño del paquete de datos.
>[!NOTE] Permite evitar el nodo oculto o expuesto.
## IEEE 802.11 DCF
Bajo el estándar existen tres modos de trasmisión:
- CSMA/CA → brodcast
- CSMA/CA+ACK → unicast
- RTS/CTS → alto tamaño (opcional)
### Principios
El estándar se basa en la espera de un tiempo aleatoria tras la finalización de la ocupación del canal, este tiempo es denotado por CW, teniendo longitudes diferentes en función de la prioridad:
1. SIFS (ACK y CTS)
2. PIFS (Coordianción)
3. DIFS (Data y RTS)
>[!important] Si la espera se ve interrumpida, el CW se pausa.
### Unicast
Se envía ACKs al terminar el periodo de SIFS (sin contención), el uso de ACKs permite la confirmación de la recepción de paquetes.
### RTS/CTS
Modo de trasmisión opcional para ayudar a enviar el problema del nodo oculto. Cuando se hace uso de este método se envía dos paquetes extra:
- RTS, paquete de solicitud de canal con tiempo estimado.
- CTS, paquete de concesión de canal con tiempo estimado.
Con estos paquetes se calcula el NAV (tiempo de RTS a ACK).
Sobre este protocolo se puede fragmentar el paquete para evitar las tramas erróneas.
## IEEE 802.11e EDCF
Mejoras en la capa MAC mediante la división del tráfico y aseguramiento de la calidad del mismo (QoS), esto se realiza mediante el HCF que sustituye el PCF y DCF.
Las categorías que se establecen son:
- Voz
- Video
- Mejor esfuerzo
- Información de fondo
Las prioridades siguen el orden anteriormente indicado y se aplican mediante la introducción de nuevos tiempos de prioridad, también se modifican los mínimos y máximos CWs para la prioridad.
# Capa PHY
## Canales radio
Para la trasmisión se hace uso de canales en dos zonas:
- 2.4 GHz
	- Mayor distancia.
	- Solapamiento.
- 5 GHz
	- Menor distancia.
	- No solapamiento.

| Canal   | 20 MHz | 40 MHz | 80 MHz | 160 MHz |
| ------- | ------ | ------ | ------ | ------- |
| 2.4 GHz | 3      | 1      |        |         |
| 5 GHz   | 25     | 12     | 6      | 2       | 
## OFDM

## Tasa