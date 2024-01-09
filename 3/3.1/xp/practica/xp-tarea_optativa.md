# Participantes
Adega Fernández Enrique, e.adega@udc.es
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
Min: $d$
$O_{1}\le 47, O_{2}\le 41, O_{3}\le 46$
# Problema 2
## Modelado
x1: horas contratadas a inspectores de tipo A.
x2: horas contratadas a inspectores de tipo B.

Min: $450\times x_1 + 100\times 0.98\times 250\times x_1+350\times x_2+100\times0.95\times150\times x_2$
$250\times x_1+150\times x_2\ge 18000$
$x_1\le64$
$x_2\le80$
## Resolución
Este ejercicio es resuelto en LPSolve, donde después de pequeñas simplificaciones se modela en el programa el problema como:
![](Pasted%20image%2020240109175046.png)
El resultado obtenido será:
![](Pasted%20image%2020240109175203.png)
Teniendo contratados a tres inspectores tipo A y diez tipos B, siendo el coste de los mismos 1766800 u.m tras tener en cuenta los posibles errores producidos por los mismos.