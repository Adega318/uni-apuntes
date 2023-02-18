# Descripción
El problema de los lectores y escritores es uno donde varios lectores intentan obtener información de una zona compartida (pudiendo hacerlo simultáneamente entre sí). Por otro lado, tenemos los escritores, que sobreescribirán la zona compartida (no pudiendo compartirla).
# Prioridad de lectores
Cuando le damos la prioridad a los lectores si hay un lector pasará antes que cualquier escritor.
## Mutex
La implementación con [[cp-seción_critica#Mutex|mutex]]:
~~~
mtx lock
mtx rlock
int readers = 0
~~~
### Escritores
~~~
lock(lock)
write()
unlock(lock)
~~~
### Lectores
```
lock(rlock)
if(readers == 0){
	lock(lock)
}
readers++
unlock(rlock)

read()

lock(rlock)
readers--
if(readers == 0){
	unlock(lock)
}
unlock(rlock)

```
## Sincronización
La implementación con [[cp-productores_consumidores#Sincronización por condiciones|sincronización]]:
```
int readers = 0, writers = 0
cnd in_use
mtx lock
```
### Escritores
```
lock(lock)
while(writers > 0 || readers > 0){
	wait(in_use, lock)
}
writers++
unlock(lock)
write()
lock(lock)
writers--

//despertamos a todos los lectores al poder leer simultáneamente
broadcast(in_use)
unlock(lock)
```
### Lectores
```
lock(lock)
while(writers > 0){
	wait(in_use, lock)
}
readers++
unlock(lock)
read()
lock(lock)
readers--
id(readers == 0){
	//solo despertamos a un escritor
	signal(in_use) 
}
unlock(lock)
```
# Prioridad de escritores
Cuando le damos la prioridad a los escritores si hay un escritor pasará antes que cualquier lector.
## Mutex
La implementación con [[cp-seción_critica#Mutex|mutex]]:
```
mtx lock
mtx rlock
mtx wlock
mtx rplock
mtx wplock
int readers = 0, writers = 0
```
### Escritores
```
lock(wlock)
if(writers == 0){
	lock(wplock)
}
writers++
unlock(wlock)

lock(lock)
write()
unlock(lock)

lock(wlock)
writes--
if(writes == 0){
	unlock(wplock)
}
unlock(wlock)
```
### Lectores
```
//parada de prioridad
//mitigar competencia de lectores con el escritor
lock(rplock)
lock(wplock)
unlock(wplock)

lock(rlock)
if(readers == 0){
	lock(lock)
}
readers++
unlock(rlock)
unlock(rplock)

read()

lock(rlock)
readers--
if(readers == 0){
	unlock(lock)
}
unlock(rlock)
```
## Sincronización
La implementación con [[cp-productores_consumidores#Sincronización por condiciones|sincronización]]:
```
mtx lock
cnd in_use
int readers = 0, writers = 0, wwait = 0
```
### Escritores
```
lock(lock)
while(writers > 0 || readers > 0){
	wwait++
	wait(in_use, lock)
	wwait--
}
writers++
unlock(lock)
write()
lock(lock)
writers--

//despertamos a todos los lectores al poder leer simultáneamente
broadcast(in_use)
unlock(lock)
```
### Lectores
```
lock(lock)
while(writers > 0 || wwait > 0){
	wait(in_use, lock)
}
readers++
unlock(lock)

read()

lock(lock)
readers--
id(readers == 0){
	//solo despertamos a un escritor
	signal(in_use)
}
unlock(lock)
```
# Tags
#2-
#2-2
#cp