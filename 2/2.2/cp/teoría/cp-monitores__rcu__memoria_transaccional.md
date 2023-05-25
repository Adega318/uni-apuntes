# Monitores
- Estado compartido
- Un conjunto de operaciones atómicas
- Un conjunto de variables de condición
- Un lock implícito

## Productores/Consumidores
```C
monitor {  
	Condition *bufferAvail, *dataAvail;  
	int num = 0;  
	int data[10];  
	
	Produce(v) {  
		monitorLock->Acquire();
		while (num == 10) {  
			bufferAvail->Wait();  
		}  
		// put v into data array  
		num++;  
		dataAvail->Signal();  
		monitorLock->Release();
	}
	
	Consume(v) {
		monitorLock->Acquire();
		while (num == 0) {  
			dataAvail->Wait();  
		}  
		// put next data array value into v  
		num--;  
		bufferAvail->Signal();  
		monitorLock->Release();
	}  
}
```
# Memoria transaccional
1. Marcamos regiones como atómicas  
2. Se realizan todas las lecturas y escrituras  
3. Comprueba si algún thread ha cambiado algún valor de los que usamos  
4. Aborta la transacción en caso afirmativo  
5. La termina en caso negativo  
6. Otro thread ve todos los cambios o ninguno

## Sintaxis
Insertar en una lista doblemente enlazada.
```C
// Insert a node into a doubly linked list atomically  
atomic {  
	newNode->prev = node;  
	newNode->next = node->next;  
	node->next->prev = newNode;  
	node->next = newNode;  
}
```
Esperar a que se cumpla una condición
```C
atomic (queueSize > 0) {  
	remove item from queue and use it  
}
```
## Retray
Se suele implementar un retray para cancelar e intentar de nuevo.
```C
atomic {  
	if (queueSize > 0) {  
		remove item from queue and use it  
	} else {  
		retry  
	}  
}
```
## Composición
Las operaciones pueden usando transacciones pueden componerse.
```C
get(Key k) {  
	atomic{seqGet(k)}  
}  

put(Key k, Value v) {  
	atomic{seqPut(k, v)}  
}  

remove(Key k) {  
	atomic{seqRemove(k)}  
}  

atomic {
	int v = map.get(k);  
	v += amount;  
	Map.put(k,v);
}
```
# RCU
Hace una copia, trabaja y mira si la copia difiere de lo guardado. Tiene gran eficiencia en lectura habitual y escritura esporádica.
- Alternativa a lock lectores/escritores 
- Lecturas tienen muy poco overhead  
- Escrituras pueden ser caras  
- Mantiene copia de datos antiguos  
- Que se reclama cuando todos los lectores antiguos han terminado

## Primitivas
```C
void rcu_read_lock(void) {}  
void rcu_read_unlock(void) {}  
void call_rcu(void (*callback) (void *), void *arg) {  
	// add callback/arg pair to a list  
}  
void synchronize_rcu(void) {  
	int cpu;  
	for_each_cpu(cpu)  
		schedule_current_task_to(cpu);  
	for each entry in the call_rcu list  
		entry->callback (entry->arg);  
}

#define rcu_assign_pointer(p, v) ({ \  
	smp_wmb(); \  
	(p) = (v); \  
})  
#define rcu_dereference_pointer(p) ({ \  
typeof(p) _value = (p); \  
smp_rmb(); /* not needed on \  
all architectures */ \  
(_value);  
})
```
# Tags
#2- 
#2-2 
#cp 