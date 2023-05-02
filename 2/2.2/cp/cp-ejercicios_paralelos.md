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

# Tags
#2- 
#2-2 
#cp 