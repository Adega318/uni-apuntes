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

Multiplicación de matrices $2N^3$ operaciones.
Multiplicación de matrices v
$(A\times B)\times v\to 2N^3+2N^2$ operaciones
$A\times (B\times v)\to 2N^2+2N^2$ operaciones
# Tags
#2- 
#2-2 
#cp 