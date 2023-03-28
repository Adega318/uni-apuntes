# Modelo de paso de mensajes
Comunicación entre procesos basado en el intercambio de mensajes. La manera de pasarlos es mediante el modelo MPI, estándar de comunicación de procesos en paralelo.
El MPI funciona mediante una red de comunicación con tipos de estructuras:
- MPMD (Multiple Program Multiple Data), cada proceso tiene una copia de toda la información.
- SPMD (Single Program Multiple Data), todos los procesos comparten un mismo banco de datos.
![[Pasted image 20230324104208.png]]
## Caracteristicas MPI

```C
int MPI_[NOMBRE]([PARAMETROS]); //declaración de mpi

MPI_Init //crear
MPI_Finalize //destruir
MPI_Comm_size //id
MPI_Comm_rank //rank
```
## Operaciones MPI
### Punto a punto
Por cada envío por parte de un proceso de haber una recepción.
```C
//envio de mensajes
int MPI_Send([void *] buff, [int] elements, [MPI_Datatype], [int] dest, [int] tag, [MPI_Comm]);

//recepción
int MPI_Send ([void *] buff, [int] count, [MPI_Datatype], [int] dest, [int] tag, [MPI_Comm]);


//ejemplo de comunicación
assert ( numprocs % 2 == 0);

if ( my_id % 2 == 0) partner = my_id +1;  
else partner = my_id -1;  

if ( my_id % 2 == 0) {  
	/* procesos pares */  
	MPI_Send (... , partner , ...) ;  
	MPI_Recv (... , partner , ...) ;  
}else{  
	/* procesos impares */  
	MPI_Recv (... , partner , ...) ;  
	MPI_Send (... , partner , ...) ;  
}
```
### Colectivas
#### Barrier
Hace esperar a los procesos hasta que todos hayan llegado.
```C
int MPI_Barrier([MPI_Comm] comm);
```
#### Bcast
```C
int MPI_Bcast([void] *buf, [int] count, )
```
# Tags
#2- 
#2-2 
#cp 