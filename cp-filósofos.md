# Descripción
El problema está presentado como unos filósofos sentados en una mesa a comer donde pueden estar comiendo o pensando, existiendo un número de tenedores menores al número de filósofos.
# Mutex
Cada tenedor es representado por un mutex, y los filósofos reclaman un tenedor y posteriormente reclaman el cubierto de su derecha para comer.
Es una solución con alta escalabilidad, ya que el filósofo solo se tiene que preocupar de sus dos cubiertos.
La desventaja son las esperas por los cubiertos con tiempos aleatorios, esto se soluciona en la siguiente implementación con la introducción de estados y la observación de los vecinos.
## Pickup
```c
int left = 
```
## Put down
```c
```
# Tags
#2-
#2-2
#cp