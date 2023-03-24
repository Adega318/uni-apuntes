# Modelo de paso de mensajes
Comunicación entre procesos basado en el intercambio de mensajes. La manera de pasarlos es mediante el modelo MPI, estándar de comunicación de procesos en paralelo.
El MPI funciona mediante una red de comunicación con tipos de estructuras:
- MPMD (Multiple Program Multiple Data), cada proceso tiene una copia de toda la información.
- SPMD (Single Program Multiple Data), todos los procesos comparten un mismo bamco de datos.
![[Pasted image 20230324104208.png]]
## Caracteristicas MPI

```C
int MPI_[NOMBRE]([PARAMETROS]); //declaración de mpi

MPI_Init
MPI_Finalize
```

# Tags
#2- 
#2-2 
#cp 