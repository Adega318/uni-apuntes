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

Para el control de congestión se establecen tres niveles de prioridad de mensaje:
- SIFS, 
- PIFS
- DIFS