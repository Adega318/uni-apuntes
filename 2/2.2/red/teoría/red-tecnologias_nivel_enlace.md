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
- Punto de acceso, punto donde se pasa de la inalámbrica a la física.
- Medio inalámbrico, radio frecuencia.
- Equipo inalámbrico, dispositivos con interfaz para conectarse a la red.

![[Pasted image 20230507194012.png]]

El BSS es un grupo de estaciones que se comunican entre sí, teniendo dos tipos:
- Independientes, tiene una comunicación directa en un grupo reducido de carácter temporal.
- Infraestructura, varios puntos de acceso conectados por infraestructura, estos puntos envían señales baliza para permitir conocer la mas cercana y potente.

Por otra parte tenemos la ESS, siendo una combinación de BSSs.
## Asociación

![[Pasted image 20230507194627.png]]

En el nivel de aplicación tenemos varios sistemas.
SSID, identificador de la red asociada a un punto de acceso.
Los equipos en una red deben asociarse a un punto de acceso, teniendo dos métodos:
- Pasivo, espera a una baliza de un punto de acceso.
- Activa, solicitud de identificación al punto de acceso.

## CSMA/CA

![[Pasted image 20230507194935.png]]

Este protocolo de comunicación es una modificación del CSMA/CD para acomodar a la naturaleza del medio de comunicación.
Cuando se quiere trasmitir se manda una petición de envió RTS indicado el tiempo de trasmisión, el punto de acceso responde con un permiso de envío CTS con el tiempo disponible para enviar. Las colisiones se resuelven con trasmisión de mensajes completos y confirmación ACK.
## Seguridad
Las redes de radiofrecuencia tiene muchos compromisos de seguridad por su naturaleza y la facilidad de escucha, se establecen varias soluciones:
- WEP, clave estática de cifrado.
- WPA, clave temporal de cifrado.
- WPA2, más seguro por el método de cifrado, clave de 128 bits.
- WPA3,  clave de 192 bits y derivación de claves independiente de la contraseña inicial.

# Tags
#2- 
#2-2 
#red 