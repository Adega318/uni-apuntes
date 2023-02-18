# Descripción
Tenemos un ejecutor que tiene un espacio de espera, cuando el ejecutor (barbero) termina con un cliente recibe al siguiente.
# Barbero simple
Único barbero que elige clientes aleatorios de la sala de espera.
## Barbero
~~~c
while(1){
	lock(mut)
	if(!customers){
		barber = SLEEPING
		wait(no_customers, mut)
	}else{
		signal(waiting_room)
		customers--
	}
	unlock(mut)
	cut()
}
~~~
## Cliente
~~~c
lock(mut)
if(customers == Max_customers){
	unlock(mut)
}else{
	if(barber == SLEEPING){
		signal(no_customers)
		barber = WORKING
	}else{
		customers++
		wait(waiting_room, mut)
	}
	unlock(mut)
	get_cut()
}
~~~
# Múltiples barberos
Múltiples barberos simples con sala de espera compartida.
## Barbero
~~~c
while(1){
	lock(mut)
	if(!customers){
		barber = SLEEPING
		wait(no_customers, mut)
	}else{
		signal(waiting_room)
		customers--
	}
	unlock(mut)
	cut()
}
~~~
## Cliente
~~~c
lock(mut)
if(customers == Max_customers){
	unlock(mut)
}else{
	if(barbers > 0){
		signal(no_customers)
		barbers--
	}else{
		customers++
		wait(waiting_room, mut)
	}
	unlock(mut)
	get_cut()
}
~~~
# Barberos con cola
Múltiples barberos con cola de espera en su sala de espera.
## Barbero
~~~c
while(1){
	lock(mut)
	if(!customers){
		barbers++
		wait(no_customers, mut)
	}else{
		signal(waiting_room)
		customers--
	}
	unlock(mut)
	cut()
}
~~~
## Cliente
~~~c
lock(mut)
if(customers == Max_customers){
	unlock(mut)
}else{
	if(barbers > 0){
		signal(no_customers)
		barbers--
	}else{
		customers++
		wait(waiting_room, mut)
	}
	unlock(mut)
	get_cut()
}
~~~
# Solución con semáforos
Los [[cp-seción_critica#Semáforos|semáforos]] complican el uso de colas y barberos concretos.
~~~c
sem customers
sem barber
sem seats

int seats = N

sem_init customers
sem_init barber
sem_init seats
~~~
## Barbero
~~~c
while(1){
	sem_wait(customers)
	sem_wait(seats)
	seats++
	sem_post(barber)
	sem_post(seats)
	cut()
}
~~~
## Cliente
~~~c
sem_trywait(seats)
if(seats > 0){
	seats--
	sem_post(customers)
	sem_post(seats)
	sem_wait(barrber)
	get_cut()
}
sem_post(seats)
~~~
# Tags
#2-
#2-2
#cp