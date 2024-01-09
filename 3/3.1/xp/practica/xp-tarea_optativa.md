# Participantes
Adega Fernández Enrique, e.adega@udc.es
Becerra Suárez Alejandro, a.becerra@udc.es
# Problema 1
| Tarea  | $O_1$ | $O_{2}$ | $O_{3}$ |
| ------ | ----- | ------- | ------- |
| $T_1$  | 18    | 16      | 12      |
| $T_2$  | 14    | 21      | 19      |
| $T_3$  | 23    | 27      | 33      |
| $T_4$  | 16    | 24      | 23      |
| $T_5$  | 17    | 24      | 24      |
| $T_6$  | 25    | 28      | 30      |
| T.disp | 47      | 41        | 46        |
## Modelado
Min: $T_1j+O_2+O_3$
$O_{1}\le 47, O_{2}\le 41, O_{3}\le 46$
## Resultado

# Problema 2
## Modelado
x1: número de inspectores de tipo A.
x2: número de inspectores de tipo B.

Min: $450\times8\times x_1 + 100\times 0.02\times 250\times8\times x_1+350\times 8\times x_2+100\times0.05\times150\times8\times x_2$
$250\times8\times x_1+150\times8\times x_2\ge 18000$
$x_1\le8$
$x_2\le10$
$x_{i}\in N$
## Resolución
Este ejercicio es resuelto en LPSolve, donde después de pequeñas simplificaciones se modela en el programa el problema como:
![](Pasted%20image%2020240109185616.png)
El resultado obtenido será:
![](Pasted%20image%2020240109185627.png)
Teniendo contratados a 8 inspectores tipo A y 2 de tipos B, sSiendo el coste de los mismos 138400 u.m tras tener en cuenta los posibles errores producidos.