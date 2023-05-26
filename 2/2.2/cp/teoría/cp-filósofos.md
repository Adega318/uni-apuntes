# Descripción
El problema está presentado como unos filósofos sentados en una mesa a comer donde pueden estar comiendo o pensando, cada filósofo comparte su tenedor derecho con el filósofo de la derecha y el izquierdo con el de la izquierda, para comer requiere de ambos.
[(wiki)](https://es.wikipedia.org/wiki/Problema_de_la_cena_de_los_fil%C3%B3sofos)
# Mutex
Teniendo N filósofos, tenemos N tenedores y un mutex para cada uno, asignaremos a cada tenedor el número del filósofo que lo tiene a su derecha.
## General
```c
mtx_t fork[N];
//I: numero filososfo
#DEFINE RF(I) ((I-1)%N)
#DEFINE LF(I) ((I+1)%N)
#DEFINE MIN(x,y) ((x)<(y)?(x):(Y))
#DEFINE MAX(x,y) ((x)>=(y)?(x):(Y))

while(true){
	mtx_lock(fork[RF(I)]);
	if(mtx_trylock(fork[LF(I)])==0) break;
	mtx_unlock(fork[RF(I)]);
	sleep(rand()%10);
}
```
## Pickup
```c
void Pick_Up(int I){
	mtx_lock(fork[MIN(RF(I), LF(I))]);
	mtx_lock(fork[MAX(RF(I), LF(I))]);
}
```
## Put down
```c
void Put_Down(int I){
	mtx_unlock(fork[RF(I)]);
	mtx_unlock(fork[LF(I)]);
}
```
# Signals & Variables
En variables usaremos solo un mutex para representar el estado de la mesa y señales. Esto llevará a una alta contención de mutex.
## General
```c
mtx_t table;
cnd_t not_fork[N];
int ph[N];
#DEFINE EATING 0
#DEFINE THINKING 1
#DEFINE SLEEPING 2
//I: numero filososfo
#DEFINE RF(I) (I==0?N-1:I-1)
#DEFINE LF(I) ((I+1)%N)
```
## Pickup
```c
void Pick_Up(int I){
	mtx_lock(table);
	while(ph[RP(I)]==EATING || ph[LF(I)]==EATING){
		ph[I]=SLEEPING;
		cnd_wait(not_fork[I], table);
	}
	ph[I]=EATING;
	mtx_unlock(table);
}
```
## Put down
```c
void Put_Down(int I){
	mtx_lock(table);
	ph[I]=THINKING;
	if(ph[RF(I)]==SLEEPING) cnd_signal(not_fork[RF(I)]);
	if(ph[LF(I)]==SLEEPING) cnd_signal(not_fork[LF(I)]);
	mtx_unlock(table);
}
```
# Tags
#2-
#2-2
#cp