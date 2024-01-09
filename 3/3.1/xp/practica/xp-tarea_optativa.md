# Participantes
Adega Fernández Enrique, e.adega@udc.es
Becerra Suárez Alejandro, a.becerra@udc.es
# Problema 1
## Modelado
$x_{ij}$: variable que indica si el ordenador j ha procesado la tarea i, tomando los valores de 0 o 1.

Min: $18x_{11}+16x_{12}+12x_{13}+14x_{21}+21x_{22}+19x_{23}+23x_{31}+27x_{32}+33x_{33}+16x_{41}$
$+24x_{42}+23x_{43}+17x_{51}+24x_{52}+24x_{53}+25x_{61}+28x_{62}+30x_{63}$

$x_{i1}+x_{i2}+x_{i3}=1$
$0\le x_{ij}\le1$
$x_{ij}\in N$
$i=1,2,3,4,5,6$     $j=1,2,3$
## Resultado
Este problema lo resolvemos usando el solver incorporado en excel, presentando los daros de la siguiente manera:
![](Pasted%20image%2020240109212208.png)
![](Pasted%20image%2020240109212227.png)
![](Pasted%20image%2020240109212237.png)
El resultado que obtenemos es un tiempo total de computación de 116, de los cuales:
- 47 corresponden al ordenador 1 que ha realizado las tareas 2, 4 y 5.
- 27 corresponden al ordenador 2 que ha realizado la tarea 3.
- 42 corresponden al ordenador 3 que ha realizado las tareas 1 y 6.
# Problema 2
## Modelado
$x_{1}$: número de inspectores de tipo A.
$x_{2}$: número de inspectores de tipo B.

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
El número de inspectores de tipo A es 8 y de tipo B 2, dándonos un gasto diario de 138400 al tener en cuenta salarios y perdidas por errores humanos.