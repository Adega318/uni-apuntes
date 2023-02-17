# Descripción
Cuando tenemos productores y consumidores compartiendo un mismo sistema, se debe implementar métodos de sincronización.
# Sincronización por condiciones
## Broadcast
El broadcast se basa en poner a esperar a los threads en un canal y despertarlos simultáneamente al encenderlo. Es una solución simple pero poco eficiente al despertar todos los threads simultáneamente.
```
cnd_t cond;

//declaración
int cnd_init(cnd_t *);
void cnd_destroy(cnd_t *);
int cnd_signal(cnd_t *);
int cnd_broadcast(cnd_t *);
int cnd_wait(cnd_t *, mtx_t *);
int cnd_timedwait(cnd_t *, mtx_t *, struct timespec *);
```
## Signals
Las señales se basan en poner a esperar a los threads en un canal, cuando se mande una señal un thread despertará. Es un método ampliamente eficiente pero difícil de implementar.
## Consideraciones
Cuando se pone a esperar a un thread, se debe confirmar la condición despertadora, ya que puede haber variado desde su despertado.