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

| 0   |     |     |     |     |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | x   |     |     |     |     |     |     |     |     |     |     |
| 2   | x   | x   |     |     |     |     |     |     |     |     |     |
| 3   | x   | x   | x   |     |     |     |     |     |     |     |     |
| 4   | x   | x   | x   | x   |     |     |     |     |     |     |     |
| 5   | x   | x   | x   | x   | x   |     |     |     |     |     |     |
| 6   | x   | x   | x   | x   | x   | x   |     |     |     |     |     |
| 7   | x   | x   | x   | x   | x   | x   | x   |     |     |     |     |
| 8   | x   | x   | x   | x   | x   | x   | x   | x   |     |     |     |
| 9   | x   | x   | x   | x   | x   | x   | x   | x   | x   |     |     |
| 10  | x   | x   | x   | x   | x   | x   | x   | x   | x   | x   |     |
| 11  | x   | x   | x   | x   | x   | x   | x   | x   | x   | x   | x   |


| P0  | P1  | P2  |
| --- | --- | --- |
| 0   | 1   | 2   |
| 3   | 4   | 5   |
| 6   | 7   | 8   |
| 9   | 10  | 11  |
|     |     |     |
| 18  | 22  | 26  |
 
26 será nuestro número máximo de operaciones.
$$S_p= \frac{T_{seq}}{T_{para}}=\frac{12\times11/2}{26}=2.54$$
$$Eff=\frac{2.54}{3}=0.85$$
### Ejer 1
#### a)
$$T_{par}= T_{clac}+T_{comm}=(256^3\times8)+(6\times T_{mensj})= 134217728+(6\times (2^{18}+4\times256^2))=137363456$$
$$S_p= \frac{T_{seq}}{T_{para}}=\frac{1024^3\times8}{137363456}=62.53$$
# 09/05/23
## Mayo 2022
### Ejer1
Datos:
- 300000 interacciones
- 1min por interacción
- 3000 fragmentos de interacciones, fragmentación de 4h (p0)
- 4 h recopilación y procesado (p0)
- (p0) no llama, solo reparte y recopila al final.
- Se debe hacer todo el reparto de manera inicial.

#### a) 
Ley de Andal:
$$Max_{sp}=\frac{T_{total}}{T_{seq}}=\frac{300000+240\times2}{240\times2}=625$$
$$T_{seq}=T_{InSeq}+T_{paralelizable}$$
625 min es la velocidad máxima.
#### b)
La descomposición es de domino, un número de fragmentos con un número de tareas.
La asignación es estática a causa de que todos los datos deben de ser repartidos inicialmente, con un modelo cíclico para fomentar el reparto uniforme de zonas de alta y baja población.
#### C)
Datos:
- tes procesos a partir del p0
- balanceo perfecto (100000 por proceso)
- 15 min por proceso parara entrega de datos por parte del p0
- recolección instantánea

Solución:
- Tiempo paralelo$$T_{para}=T_{seq}+T_{comp}+T_{com}=(240\times2)+100000+(15\times3)=100525\ min$$
- Speedup$$Speedup= \frac{T_{seq}}{T_{para}}=\frac{30000+240\times2}{100525}=2.99$$
- Eficiencia$$Eficiencia = \frac{Speedup}{Nproces}=\frac{2.99}{4}=0.75$$
- Coste$$Coste= T_{para}\times Nproces=100525\times4=402100$$
- Sobrecarga$$Sobrecarga=Coste-T_{seq}=402100-300480=101620\ min$$
#### d)
Se podría comenzar el procesamiento de los datos a medida que los procesos completen fragmentos de su tarea.
### Ejer 2
Datos:
- Matriz A de $C\times P$ mide corrupción por persona
- Matrizes X e Y de tamaños $P\times M \ \ P\times N$ respectivamente que miden las personas a ignorar
- Algoritmo de calculo:
	![[Pasted image 20230509111921.png]]

#### a)
#### d)
Realizaríamos por bloques de filas de A pasando X e Y al completo.
```C
double *A, *X, *Y, *I;  
int rank, C, P, M, N, i, j, k;  
MPI_Init(&argc, &argv);  
MPI_Comm_rank(MPI_COMM_WORLD, &rank);  

if(!rank) {  
	read(&A,&X,&Y,&C,&P,&M,&N);  
}  

MPI_Bcast(&C, 1, MPI_INT, 0, MPI_COMM_WORLD);  
MPI_Bcast(&P, 1, MPI_INT, 0, MPI_COMM_WORLD);  
MPI_Bcast(&M, 1, MPI_INT, 0, MPI_COMM_WORLD);  
MPI_Bcast(&N, 1, MPI_INT, 0, MPI_COMM_WORLD);  

if(rank) {  
	A = (double *)malloc(sizeof(double) * C/10 * P);  
	X = (double *)malloc(sizeof(double) * P * M);  
	Y = (double *)malloc(sizeof(double) * P * N);  
}  

I = (double *)malloc(sizeof(double) * C);  
MPI_Scatter(A, C/10 * P, MPI_DOUBLE,  
	rank ? A : MPI_IN_PLACE, C/10 * P, MPI_DOUBLE, 0, MPI_COMM_WORLD);  
MPI_Bcast(X, P * M, MPI_DOUBLE, 0, MPI_COMM_WORLD);  
MPI_Bcast(Y, P * N, MPI_DOUBLE, 0, MPI_COMM_WORLD);  

for(i = 0; i < C/10; i++) {  
	I[i]=0;  
	for(j = 0; j < P; j++) {  
		for(k=0; k < M; k++)  
			I[i] += A[i * P + j] * X[j * M + k];  
		for(k=0; k < N; k++)  
			I[i] -= A[i * P + j] * Y[j * N + k];  
	}  
}  

MPI_Gather(rank ? I : MPI_IN_PLACE, C/10, MPI_DOUBLE,  
	I, C/10, MPI_DOUBLE, 0, MPI_COMM_WORLD);  

if(!rank) print(I, C);  

MPI_Finalize();
```
# 12/05/23
## Julio 2022
### Ejer 1
#### a)
Ley de Andal:$$Max_{sp}=\frac{T_{total}}{T_{seq}}=\frac{0.05\times t+0.95\times t}{0.05\times t}=20$$
#### b)

![[Pasted image 20230512104200.png]]

Grados de concurrencia:
- Máximo, número máximo de tareas simultaneas durante la ejecución, en este caso 7 (1,4,5,7,8,9,10)
- Medio:$$GMC=\frac{\sum_p}{Peso\ camino\ critico}=\frac{200}{10+20\times2+30\times2}=1.82$$

#### c)

| p0  | t0  | t2  | t2  | t2  | t3  | t3  | t6  | t6  | t6  | t8  | t8  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| p1  |     | t1  | t1  |     | t4  |     | t5  | t5  |     | t9  |     |
| p2  |     |     |     |     |     |     | t7  | t7  |     | t10 |     |

#### d)
Speedup:
Eficiencia:
#### e)
Tres proceso es el número mínimo y necesario para la completa paralización de las partes paralelizables.
### Ejer 2
#### a)
#### b) 
```C
char *seq1, *seq2;  
int numIgual, resParcial;  

if(rank == 0){  
	seq1 = (char *)malloc(sizeof(char) * L);  
	seq2 = (char *)malloc(sizeof(char) * L);  
	leeDeDisco(seq1, seq2, L);  
} else {  
	seq1 = (char *)malloc(sizeof(char) * L/numP);  
	seq2 = (char *)malloc(sizeof(char) * L/numP);  
}  

resParcial = 0;  

MPI_Scatter(seq1, L/numP, MPI_CHAR,  
	rank ? seq1 : MPI_IN_PLACE, L/numP, MPI_CHAR, 0, MPI_COMM_WORLD);  
MPI_Scatter(seq2, L/numP, MPI_CHAR,  
	rank ? seq2 : MPI_IN_PLACE, L/numP, MPI_CHAR, 0, MPI_COMM_WORLD);  
	
for(int i = 0; i < L/numP; i++)  
	if(seq1[i] == seq2[i]) resParcial++;  
		
MPI_Reduce(&resParcial, &numIgual, 1, MPI_INT, MPI_SUM, 0, MPI_COMM_WORLD);  

if(rank == 0) escribeResultado(numIgual);
```
#### c)
Datos:
- topo logia de anillo, conexión con dos vecinos

Se necesitaran $\frac{numP}{2}$ truncado. 
#### d)
```C
int soyFinal = 0;  
if((rank == numP/2) || (rank == numP/2+1)) soyFinal = 1;

int caminoAscendente = 0;  
if(rank <= numP/2) caminoAscendente = 1;

if(rank == 0) {  
	MPI_Send(A, L, MPI_CHAR, 1, 0, MPI_COMM_WORLD);  
	MPI_Send(A, L, MPI_CHAR, numP-1, 0, MPI_COMM_WORLD);  
} else {  
	MPI_Recv(A, L, MPI_CHAR, MPI_ANY_SOURCE, 0, MPI_COMM_WORLD, null);  
	if(soyFinal == 0){  
		if(caminoAscendente == 1){  
			MPI_Send(A, L, MPI_CHAR, rank+1, 0, MPI_COMM_WORLD);  
		} else {  
			MPI_Send(A, L, MPI_CHAR, rank-1, 0, MPI_COMM_WORLD);  
		}  
	}  
}
```
# Tags
#2- 
#2-2 
#cp 