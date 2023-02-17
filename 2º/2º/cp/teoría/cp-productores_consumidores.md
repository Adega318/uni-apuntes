# Descripción
Cuando tenemos productores y consumidores compartiendo un mismo buffer, se debe implementar métodos de sincronización para gestionar su uso.
## Mutex
la implementación mediante [[cp-seción_critica#Mutex|mutex]] presenta el problema de la espera activa, donde se está comprobando constantemente si se libera.
### Consumidor
```
while(1) {  
	elemento e; int removed;  
	removed=0;  
	do {  
		mtx_lock(buffer_lock);  
		if(elements()>0) {  
			e = remove();  
			removed=1;  
		}  
		mtx_unlock(buffer_lock);  
	} while(!removed);  
	fun();
}
```
### Productor
```
mtx_t buffer_lock;
while(1) {
	elemento e = crear_elemento(); int inserted;
	inserted =0;
	do {
		mtx_lock(buffer_lock);
		if(elements()<buffer_size()) {
			insert(e);
			inserted=1;
		}
		mtx_unlock(buffer_lock);
	} while(!inserted);
}
```
# Sincronización por condiciones
## Wait atómico
Los wait deben de ser atómicos, si no se cumple el estado del buffer puede cambiar  
antes de que el thread duerma, lo que causara [lost wakeup]()
## Broadcast
El broadcast se basa en poner a esperar a los threads en un canal y despertarlos simultáneamente al encenderlo. Es una solución simple pero poco eficiente al despertar todos los threads simultáneamente.
```
cnd_t cond;

//declaración
int cnd_init(cnd_t *);

//eliminación
void cnd_destroy(cnd_t *);

//despertar
int cnd_broadcast(cnd_t *);

//dormir
int cnd_wait(cnd_t *, mtx_t *);
//dormir limitado
int cnd_timedwait(cnd_t *, mtx_t *, struct timespec *);
```
### Consumidor
### Productor
## Signals
Las señales se basan en poner a esperar a los threads en un canal, cuando se mande una señal un thread despertará. Es un método ampliamente eficiente pero difícil de implementar.
```
cnd_t cond;

//declaración
int cnd_init(cnd_t *);

//eliminación
void cnd_destroy(cnd_t *);

//despertar
int cnd_signal(cnd_t *);

//dormir
int cnd_wait(cnd_t *, mtx_t *);
//dormir limitado
int cnd_timedwait(cnd_t *, mtx_t *, struct timespec *);
```
### Consumidor
### Productor
## Consideraciones
Cuando se pone a esperar a un thread, se debe confirmar la condición despertadora, ya que puede haber variado desde su despertado.
