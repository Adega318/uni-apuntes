# Conceptos
## Niveles de paralelismo
Sucesivos niveles de complejidad de paralelismo construidos sobre los anteriores.
- Hardware, replicación de recursos del hardware.
- Software
	- Básico, gestión del nivel de hardware.
	- Intermedio, herramientas para la implementación de aplicaciones paralelas.
	- Alto, núcleos computacionales con ejecución paralela.
- Aplicación, aplicaciones implementadas sobre los anteriores niveles.
## Dependencias de datos
Las tareas deben de carecer de dependencias para poder funcionar en paralelo, existiendo las siguientes:
- RAW, A tiene dependencia de B si requiere una de las salidas de B para operar.
- WAR, A anti depende B si A modifica una variable usada por B.
- WAW, A y B son dependientes si generan el mismo dato.
# Modelo de paso de mensajes
Comunicación entre procesos basado en el intercambio de mensajes. La manera de pasarlos es mediante el modelo MPI, estándar de comunicación de procesos en paralelo.
El MPI funciona mediante una red de comunicación con tipos de estructuras:
- MPMD (Multiple Program Multiple Data), cada proceso tiene una copia de toda la información.
- SPMD (Single Program Multiple Data), todos los procesos comparten un mismo banco de datos.

![[Pasted image 20230324104208.png]]

## Conceptos Básicos
```C
int MPI_[NOMBRE]([PARAMETROS]); //declaración de mpi

MPI_Init //crear
MPI_Finalize //destruir
MPI_Comm_size //númerode procesos
MPI_Comm_rank //rank
```
## Mensajes MPI
### Punto a punto
Por cada envío por parte de un proceso de haber una recepción.
```C
//envio de mensajes
int MPI_Send([void *] buff, [int] elements, [MPI_Datatype] datatype, [int] dest, [int] tag, [MPI_Comm] comm);

//recepción
int MPI_Recv ([void *] buff, [int] count, [MPI_Datatype] datatype, [int] source, [int] tag, [MPI_Comm] comm, [MPI_Status*] status);


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
Funciones que deben ejecutar todos los procesos.
#### Barrier
Hace esperar a los procesos hasta que todos hayan llegado.
```C
int MPI_Barrier([MPI_Comm] comm);
```
#### Bcast
Obliga a todos a recibir un mensaje, mediante la llamada *Bcast*.
```C
int MPI_Bcast([void *] buf, [int] count, [MPI_Datatype] datatype, [int] root, [MPI_Comm] comm);
```
#### Scatter
Distribuye el elemento en trozos iguales de tamaño *sendcnt*, la versión variable es *scatterv*.
```C
MPI_Scatter([void *] buff, [int] sendcnt, [MPI_Datatype] sendtype, [void *] recvbuff, [int] recvcnt, [MPI_Datatype] recvtype, [int] root, [MPI_Comm] comm);
```
Con la terminación v se puede asignar tamaños concretos para cada proceso, definido en sendcounts (cuanto para cada uno), displs (desplazamiento cuando empieza cada uno) y recvcount (cantidad recivida).
```C
int MPI_Scatterv([const void *] sendbuf, [const int *] sendcounts, [const int *] displs, [MPI_Datatype] sendtype, [void *] recvbuf, [int] recvcount, [MPI_Datatype] recvtype, [int] root, [MPI_Comm] comm);
```
#### Gather
Recibe en *root* los elementos de todos los procesos.
```C
MPI_Gather([void *] buff, [int] sendcnt, [MPI_Datatype] sendtype, [void *]recvbuff, [int] recvcnt, [MPI_Datatype] recvtype, [int] root, [MPI_Comm] comm);
```
Con la terminación v se puede recibir cantidades distintas por cada uno, sendcount (número enviado), recvcounts (número recibido por cada uno), displs (desplazamiento de cada uno para la deconstrucción).
```C
int MPI_Gatherv([const void *] sendbuf, [int] sendcount, [MPI_Datatype] sendtype, [void *] recvbuf, [const int *] recvcounts, [const int *] displs, [MPI_Datatype] recvtype, [int] root, [MPI_Comm] comm)
```
#### Reduce
Recibe de todos y hace la operación, tiene una versión *all* donde manda el resultado a todos.
```C
int MPI_Reduce([void *] buff, [void *] recvbuff, [int] count, [MPI_Datatype] datatype, [MPI_Op] op, [int] root, [MPI_Comm] comm);
```
# Análisis de algoritmos
## Conceptos
- Tiempo de ejecución paralelo, tiempo desde el comienzo del primer procesador al final del ultimo.
### Ley de Amdahl
Medición del límite de ganancia de velocidad obtenida en la implementación paralela.
$F_{s} =$ implementación secuencial.
$F_{p}=$ implementación paralela.$$A_{p}= \frac{T_{secuencial}}{T_{paralelo}(p)}=\frac{F_s+F_p}{F_s+\frac{F_p}{p}}$$
También calcula la aceleración máxima teórica:$$A_{max}=\lim_{p\to\infty}\frac{T_{secuencial}}{T_{paralelo}(p)}=\lim_{p\to\infty}\frac{F_s+F_p}{F_s+\frac{F_p}{p}}=\frac{F_s+F_p}{F_s}$$
Esta métrica es puramente teriaca sin base de ejecución.
## Medidas de prestaciones
### Speedup
Métrica con valores entre 0 y p pudiendo superarlo (mejora de los fallos de caché), es la mejora sobre la versión original en función del numero de procesadores.$$Speedup(p)=\frac{T_{secuencial}}{T_{paralelo}(p)}$$
### Eficiencia
Métrica de mejora por procesador, con valores entre 0 e 1 pudiendo superar a causa del Speedup.$$Eficiencia(p)=\frac{Speedup(p)}{p}=\frac{T_{secuencial}}{p\times T_{paralelo}(p)}$$
### Coste/Overhead
Tiempo dedicado por el sistema para paralelizar la operación.$$Coste=p\times T_{paralelo}(p)$$
Deberá de ser equivalente al secuencial pero suele ser mayor.$$Overhead=Coste-T_{secuencial}$$
### Estabilidad
Es la medida de el efecto del aumento de recursos, pudiendo caer en dos categorías:
- Fuerte, el aumento de recursos no afecta a la eficiencia del algoritmo.
- Débil, el aumento de recursos afecta a la eficiencia.
# Tags
#2- 
#2-2 
#cp 