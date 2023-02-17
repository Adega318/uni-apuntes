# Descripción
Una sección crítica es una zona de memoria compartida varios agentes.
# Exclusión mutua
La exclusión mutua es el proceso donde el acceso a la sección crítica es excluyente del resto de agentes.
# Instrucciones atómicas
Las instrucciones atómicas con la cuales permiten el bloqueo y desbloqueo para la gestión de la sección crítica.
## Mutex
Los mutex son variables que permiten el bloqueo y espera a desbloqueo.
```
enum{
	mtx_plain,
	mtx_recursive,
	mtx_timed
};
mtx_t *mutex;

//declaración
int mtx_init(mtx_t *mutex, int type);

//eliminación
void mtx_destroy(mtx_t *mutex);

//bloqueo
int mtx_lock(mtx_t *mutex);
//bloqueo con tiempo
int mtx_timedlock(mtx_t *mutex, struct timespec *time);
//intento de bloqueo
int mtx_trylock(mtx_t *mutex);

//desbloqueo
int mtx_unlock(mtx_t *mutex); 
```
## Semáforos
Los semáforos son variables de tipo int sobre las que se puede esperar a su llegada a 0 y actualizar valor.
```
sem_t *sem;
//sem tiene que encontrarse en u espacio de memoria compartida por los procesos

//declaración
int sem_init(sem_t *sem, int pshared, unsigned int value);  

//eliminación
int sem_destroy(sem_t *sem);

//espera
int sem_wait(sem_t *sem);
//intento de espera
int sem_trywait(sem_t *sem);
//espera con tiempo
int sem_timedwait(sem_t *sem, const struct timespec *abs_timeoout);

//aztualización del valor
int sem_post(sem_t *sem);
```