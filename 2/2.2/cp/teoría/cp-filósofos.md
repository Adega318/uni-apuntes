# Descripción
El problema está presentado como unos filósofos sentados en una mesa a comer donde pueden estar comiendo o pensando, cada filósofo comparte su tenedor derecho con el filósofo de la derecha y el izquierdo con el de la izquierda, para comer requiere de ambos.
[(wiki)](https://es.wikipedia.org/wiki/Problema_de_la_cena_de_los_fil%C3%B3sofos)
# Mutex
Teniendo N filósofos, tenemos N tenedores y un mutex para cada uno, asignaremos a cada tenedor el número del filósofo que lo tiene a su derecha.
## General
```c
mtx_t fork[N];
//I: numero filososfo
#DEFINE RF(I) (I)
#DEFINE LF(I) ((I+1)%N)
#DEFINE MIN(x,y) ((x)<(y)?(x):(Y))
#DEFINE MAX(x,y) ((x)>=(y)?(x):(Y))

while(true){
	mtx_lock(fork[RF(I)]);
	if(mtx_trylock(fork[LF(I)])==0) break;
	mtx_unlock(fork[RF(I)]);
	
}
```
## Pickup
```c
Pick_Up(int I){
	mtx_lock(fork[MIN(RF(I), LF(I))]);
	mtx_lock(fork[MAX(RF(I), LF(I))]);
}
```
## Put down
```c
Put_Down(int I){
	mtx_unlock(fork[RF(I)]);
	mtx_unlock(fork[LF(I)]);
}
```
## Can_i_eat
```c

```
# Mutex
Cada tenedor es representado por un mutex, y los filósofos reclaman un tenedor y posteriormente reclaman el cubierto de su derecha para comer.
Es una solución con alta escalabilidad, ya que el filósofo solo se tiene que preocupar de sus dos cubiertos.
La desventaja son las esperas por los cubiertos con tiempos aleatorios, esto se soluciona en la siguiente implementación con la introducción de estados y la observación de los vecinos. Esto puede llevar a inanición, por lo tanto, implementamos un registro de la última vez que comí, haciendo que se le dé prioridad a los más hambrientos (función can_i_eat).
## Pickup
```c

```
## Put down
```c

```
## Can_i_eat
```c

```
## Comparación de implementaciones
Las implementaciones subóptimas se encuentran en los apuntes.
# Tags
#2-
#2-2
#cp