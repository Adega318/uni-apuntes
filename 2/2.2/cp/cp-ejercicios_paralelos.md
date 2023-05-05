# 28/04/23
## Ejer1
Enunciado:
- 17 procesadores $P_i$
- $P_0$ no tiene hardware para punto flotante pero es el único con E/S
- No se solapan comunicaciones
- Solo comunicación punto a punto
Objetivo:
- calculo de $r=A\times B\times v$ siendo A y B matrices $N\times N$  elementos, y v y r vectores de N elementos, siendo N divisible por 16.
- Datos en punto flotante.
### a)
Tiempo en calcular $r=(A\times B) \times v$ y $r=A\times (B \times v)$ con solo un procesador de cálculos.

Solución:
```ad-summary
title: nota
Multiplicación de matrices $2N^3$ operaciones y multiplicación de matrices con vectores $2N^2$ operaciones.
```
$(A\times B)\times v\to 2N^3+2N^2$ operaciones
$A\times (B\times v)\to 2N^2+2N^2$ operaciones

### b)
Con las restricciones de MPI crea un:
```C
myAllGather(const double *input, double *output, int elemsPerProc)
```
Para ser llamada por los procesos de 1 a 16 haciendo:
- enviar elemsPerProc a todos los procesos en myAllGather.
- guardar los recibidos en output.

Solución:
```C
void myAllGather
	int i, rank;
	MPI_Status status;
	MPI_Comm_rank(MPI_COMM_WORLD, &rank);
	for(i=1; i<rank; i++){
		MPI_Recv(output+(i-1)*elemsPerProc, elemsPerProc, i);
		MPI_Send(input, elemsPerProci);	
	}
	for(i=rank+1; i<=16; i++){
		MPI_Send(input, elemsPerProc, i)
		MPI_Recv(output+(i-1)*elemsPerProc, i)
	}
	memcpy(output+(rank-1)*elemsPerProc, input, elemsPerProc*sizeof(double))
```
# 02/05/23
## Julio 17
### Ejer 1
#### a)
Dado que es una matriz $500\times 500$ y una malla de 48 procesos $6 \times 8$.
Igualamos las mallas $\frac{500}{6}= 84$ por fila y $\frac{500}{8}= 63$ por columna dando 5212 cálculos por proceso, a excepción de los últimos que se llevan el resto, $80\times 11=880$ para el ultimo y . 
#### b)
Proceso con el $(200, 200)$.
Cae en el procesos $(2,3)$, matriz de 
#### c)
Como no hay sobrecarga ($T_{par}= T_{calc}+T_{com}+T_{sys}=84\times63\times1s+0+0= 5212$) el speedup es:$$S_p=\frac{T_{seq}}{T_{par}}=\frac{500\times500\times1s}{5212}=47.24$$
#### d)
Como ahora hay comunicación:$$T_{par}= T_{calc}+T_{com}+T_{sys}=84\times63\times1s+(48\times100+500\times500)\times0.001+0= 5796.21$$
Por lo tanto el speedup pasa a ser:$$S_p=\frac{T_{seq}}{T_{par}}=\frac{500\times500\times1s}{5796.21}=43.13$$
#### e)
El cero distribuye la primera fila con su columna correspondiente a cada proceso que lo reparte a toda su columna.
### Ejer 2
#### a) (se pregunta a menudo)
Una híbrida entre:
- Funcional
	- Matriz, se reparte por dominio.
	- Bucle, se reparte por dominio
#### b) 
1. p0 lee A y v
2. broadcast N
3. se reserva espacio para v
4. brodcast v
5. se calcula la cantidad de gupos para cada proceso N/P
6. scatter de N/P partes de A
7. calculo de r=v*A
8. calculo
9. reduce de los procesos
10. gather en v

# 05/05/23
## Mayo 2018
### Ejer 2
Comparar pares de un conjunto de 100000 elementos con 1500 datos de cada uno y una función simétrica con un coste de comparación fijo. Tenemos el siguiente algoritmo:
```C
gato_t gatos [ N ];
double res [ N ][ N ];
// inicializa el array de elementos
lee ( gatos );
// aplica la funci ́on f
for ( i =0 ; i < N ; ++ i )
	for ( j =0 ; j < i ; ++ j )
		res [ i ][ j ] = f ( gatos [ i ] , gatos [ j ]);
// escribe el resultado
escribe ( res );
```
Dándonos como resultado:

![[Pasted image 20230505104107.png]]

Realizando $N(N-1)/2$ comparaciones.
#### Consideraciones
- Número de gatos y comparaciones múltiplos del numero de procesos.
- Comunicación despreciable
- P0 I/O

#### a)
Descomposición de domino, asignando tareas de manera cíclica para aumentar el balanceo.
#### b)
```C
int block_size = N / n_procs ;  
double res_local [ block_size ][ N ];

if ( root )  
	lee ( gatos );

MPI_Bcast ( gatos, N, MPI_GATO, 0, MPI_COMM_WORLD );  
/* el reparto del bucle principal es similar al utilizado  
* en la primera pr ́actica de la asignatura para el c ́alculo  
* de pi */  
int i_local = 0;  
for ( i = rank ; i < N ; i += n_procs ){  
	for ( j =0 ; j < i ; ++ j )  
		res_local [ i_local ][ j ] = f ( gatos [ i ] , gatos [ j ]);  
	++ i_local ;  
}

//sustituible por gather y comentario de que se deve de ordenar la matriz.
if (! root ){  
	// enviamos el bloque calculado al proceso root  
	MPI_Send ( res_local, N * block_size, MPI_DOUBLE, 0, 1, MPI_COMM_WORLD );  
}else{  
	for ( proc = 0; proc < n_procs ; proc ++){  
		// recibimos cada bloque excepto el nuestro propio  
		if ( proc > 0)  
			MPI_Recv ( res_local, N * block_size, MPI_DOUBLE, proc, MPI_ANY_TAG, 
				MPI_COMM_WORLD, MPI_STATUS_IGNORE );
				
		// y lo ordenamos en la matriz resultado  
		for ( i =0; i < block_size ; i ++){  
			memcpy ( res [ proc + i * n_procs ], res_local [ i ],
				N * sizeof( double ));  
		}  
	}  
	escribe ( res );  
}
```
#### c)
| P0  | P1  | P2  |
| --- | --- | --- |
| 0   | 1   | 2   |
| 3   | 4   | 5   |
| 6   | 7   | 8   |
| 9   | 10  | 11  |
|     |     |     |
| 18  | 22  | 26  | 
$$S_p= \frac{T_{seq}}{T_{para}}=\frac{12\times11/2}{26}=2.54$$
$$Eff=\frac{2.54}{3}=0.85$$
### Ejer 1
#### a)

# Tags
#2- 
#2-2 
#cp 