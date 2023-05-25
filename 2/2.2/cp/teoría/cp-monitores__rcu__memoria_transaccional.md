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
		while (num == 10) {  
		bufferAvail->Wait();  
	}  
	// put v into data array  
	num++;  
	dataAvail->Signal();  
}

Consume(v) {  
	while (num == 0) {  
		dataAvail->Wait();  
	}  
		// put next data array value into v  
		num--;  
		bufferAvail->Signal();  
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

Se suele implementar un retray para cancelar e intentar de nuevo.
Este método permite la composición de funciones, al no hacer empleo de mutex.
# RCU
Hace una copia, trabaja y mira si la copia difiere de lo guardado. Tiene gran eficiencia en lectura habitual y escritura esporádica.
- Alternativa a lock lectores/escritores 
- Lecturas tienen muy poco overhead  
- Escrituras pueden ser caras  
- Mantiene copia de datos antiguos  
- Que se reclama cuando todos los lectores antiguos han terminado

# Tags
#2- 
#2-2 
#cp 