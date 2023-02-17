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
//bloqueo
int mtx_timedlock(mtx_t *mutex, struct timespec *time);
int mtx_trylock(mtx_t *mutex);
int mtx_unlock(mtx_t *mutex); 
```
## Semáforos