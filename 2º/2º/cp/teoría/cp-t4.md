# Descripción
# Prioridad de lectores
## Mutex
~~~
mtx lock
mtx rlock
int readers = 0
~~~
### Lectores
~~~
lock(lock)
write()
unlock(lock)
~~~
### Escritores
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
## Señales
```
int readers = 0, writers = 0

```
### Lectores
### Escritores
# Prioridad de escritores
## Mutex
### Lectores
### Escritores
## Señales
### Lectores
### Escritores