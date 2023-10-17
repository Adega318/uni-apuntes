# Capa de red inalámbrica

## Problemas de comunicación

### Nodo oculto

En una red con tres nodos donde dos tiene comunicación a uno y no entre ellos, esto lleva a la solapación de las comunicaciones con el nodo común.

### Nodo expuesto

Un nodo se comunica con otros dos inconexos, este nodo transmite a uno de ellos y el otro nodo inconexo no puede trasmitir a un tercero por la trasmisión del nodo medio pese a no ocasionar colisiones.

## Estándar 802.11 DCF

Este estándar de comunicación integra tres sistemas de comunicación principales:

- CSMA/CA -> brodcast
- CSMA/CA+ACK -> unicast
- RTS/CTS -> unicast de alto tamaño (opcional)

El control de comunicación se basa en la espera de un tiempo sin comunicaciones para comenzar a trasmitir. Si durante el tiempo de espera se escucha comunicación se resetea el temporizador y se le añade un numero aleatorio en un rango variable en función de la congestión llamado **CW**, en caso de una segunda interrupción el tiempo restante de CW es el nuevo CW. Los varios niveles de prioridad del tiempo base son:

1. SIFS
2. PIFS
3. DIFS

Cuando se hace uso de ACKs se envían los mismos usando SIFS para el control de colisiones.

### RTS/CTS

Cuando se intenta trasmitir paquetes de alto tamaño se hace uso del protocolo MACA que solicita la red con un paquete RTS que requiere la respuesta por parte del receptor de un CTS tras el cual se comienza a trasmitir, el tiempo trascurrido desde el RTS hasta el fin de la comunicación se conoce como NAN.

### IEE 802.11e
Mejoras en la capa MAC mediante la división del trafico y aseguramiento de la calidad del mismo, esto se realiza mediante el HCF que sustituye el PCF y DCF.
Las categorías que se establecen son:
- Voz
- Video
- Mejor esfuerzo
- Información de fondo

Las prioridades siguen el orden anteriormente indicado y se aplican mediante la introducción de nuevos tiempos de prioridad, tambien se modifican los minimos y maximos CWs para la priori