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
>[!]Esta estrategia no detecta colisiones.
## MACA

## IEEE 802.11 DCF
## IEEE 802.11e EDCF
# Capa PHY
## Modulaciones y códigos de canal