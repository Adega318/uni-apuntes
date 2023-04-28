Para que un algoritmo aumente la eficiencia al ser paralelizado como mínimo debería de ser de un orden de magnitud superior en computación que en volumen de datos.
# Multiplicación de matrices

![[Pasted image 20230428084453.png]]

## Descomposición y asignación
Dividimos la matriz A en bloques de filas de tamaño dependiente del número de procesos y la B completa.
## Reparto de datos
Entrada: matrices A y B, dimensiones $n\times n$ sólo disponibles en el proceso 0  
Suponemos que todos los procesos disponen de MPI COMM WORLD, my id, numprocs  
```C
// Por simplicidad se omite la declaración de variables

// Distribución de n y la matriz B  
MPI_Bcast( &n, 1, MPI_INT, 0, MPI_COMM_WORLD );
MPI_Bcast( B, n*n, MPI_DOUBLE, 0, MPI_COMM_WORLD );

// Cálculo del número de filas por proceso  
rows = ( n + numprocs - 1 ) / numprocs;
// Corrección del tamaño de A para scatter  
if( (my id == 0) && (n % numprocs) ) {  
	A = (double *)realloc( A, sizeof(double)*n*numprocs*rows );
}

// Reserva de memoria para las submatrices local  
// Nota: el proceso (p-1) puede sobrerreservar  
Alocal = (double*)malloc( sizeof(double)*rows*n );  
xlocal = (double*)malloc( sizeof(double)*rows*n );

// Scatter de los datos de A  
MPI_Scatter( A, rows*n, MPI_DOUBLE, Alocal, 
	rows*n, MPI_DOUBLE, 0, MPI_COMM_WORLD );
// Corrección del número de filas en (p-1)  
if( my id == numprocs-1 ) {  
	rows = n - rows*(numprocs-1);
}

// Lazo computacional  
for( i = 0; i < rows; ++i ) {  
	for( j = 0; j < n; ++j ) {  
		xlocal[i][j] = 0;
		for( k = 0; k < n; ++k ) {  
			xlocal[i][j] += Alocal[i][k] * B[k][j];
		}  
	}  
}

// (Sobre)reserva para el vector x en el proceso 0  
if( my id == 0 ) {  
	x = (double*)malloc(  
	sizeof(double)*n*numprocs*rows );  
}  
// Gather de todos los datos  
MPI_Gather( xlocal, n*rows, MPI_DOUBLE, x, n*rows,  
	MPI_DOUBLE, 0, MPI_COMM_WORLD );
```
# Tags
#2- 
#2-2 
#cp 