# Conceptos
- Broadcast, canal compartido con múltiples destinatarios.
- Punto a punto, canales de comunicación directos.
- Protocolo, conjunto de mensajes válidos.
- Arquitectura, conjunto de protocolos.

# Redes
## Circuitos
Cuando dos nodos se comunican se establece una conexión terminal a terminal.
- Recursos por reserva.
- Reserva persistente durante la sesión.

### División de frecuencias (FMD)

![[Pasted image 20230417182206.png]]

### División en el tiempo (TDM)

![[Pasted image 20230417182222.png]]

## Paquetes
Características:
- Sin reserva.
- Los recursos bajo demanda, con posible espera por ellos.
- Mensajes divididos en paquetes.

### Datagrama
- Datagrama, envío en función de la dirección de envío, sin mantener información sobre los routers.
- Circuito virtual, envío basándonos en el número de circuito virtual, Los conmutadores mantienen información del estado de las comunicaciones entrantes: interfaz de entrada - etiqueta de entrada – interfaz de salida.

### Tipos de retardo

![[Pasted image 20230417183117.png]]

- Procesamiento, tempo de examinado de la cabecera para conocer el siguiente destino.
- Cola, tiempo de espera para la trasmisión.
- Trasmisión, tiempo de trasmisión del mensaje.
- Propagación, tiempo de movimiento por el router.

## Acceso y medio físico
Tres clases de acceso:
- Residencial, usa un proveedor con banda ancha, cable, modem o satélite.
- Empresa, conexión directa a la web utilizando LANs.
- Inalámbrico, conexión mediante redes de datos (2G, 3G, ...)

# Arquitectura
La arquitectura es la manera en la que estructuramos las comunicaciones, se utiliza el modelo OSI.

![[Pasted image 20230417190502.png]]

## Niveles
### Físico
Trasmisión de bits.
### Enlace

![[Pasted image 20230417190750.png]]

- Tramas, conjuntos de bits.
- Direcciones de enlace.

### Red
- Conjunto de enlaces que forma un extremo a extremo.
- Comunicación entre sistemas con cálculo de rutas.
- Direcciones de red.
- Enrutamiento, planificación del orden de trasmisión de los paquetes.

### Transporte
* Servicios de extremo a extremo
	* TCP
	* UDP

### Sesión y presentación
- No comunes.
- Sesión, envió de datos urgentes y sincronización.
- Presentación, oculta las diferencias de formato entre aplicaciones.

### Aplicación
- Aplicaciones de red (www, email, ...)

# Tags
#2- 
#2-2 
#red