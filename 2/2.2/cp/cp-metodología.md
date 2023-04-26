# Descomposición de tareas
## Dominio
Técnica usada sobre grandes estructuras, consiste de dos pasos:
- Troceado de datos
- Asociación de la computación
### Regla del propietario
Los procesos dependientes de un conjuntos de datos es responsabilidad del propietario de esos datos, en caso de necesitar más datos no poseídos puede incumplirse.
## Funcional
Descompones las tareas de calculo del algoritmo en distintos procesos, esta descomposición dará a procesos con dependencias entre si.
1. Establecer dependencias.
2. Asignar las partes sin incumplir las dependencias
## Recursiva
División del problema en procesos de manera recursiva con un criterio de parada para ejecución, se divide hasta que sea de tamaño manejable y al terminar se reporta al superior.
## Especulativa
Se basan en partes de código excluyentes dependientes de otra tarea lo que se puede resolver con la ejecución simultanea de las partes excluyentes y elección de la correcta (desperdicio de recursos a cambio de tiempo).
## Tareas
Se descompone el programa en tareas de árbol, cada tarea es independiente internamente, teniendo su propio estilo de descomposición.
Se pueden establecer las tareas de dos maneras:
- Estática, si tenemos un problema estable con iteraciones determinado podemos definir las tareas de manera permanente.
- Dinámica, se crean tareas en el código en función del progreso del programa.
Es importante el balanceo de carga entre los distintos procesadores.
# Asignación de tareas
## Asignación estática
Toma de decisiones de asignación previa a la ejecución sin producir sobrecarga en ejecución.
### Descomposición de dominio
Sobre algoritmos con dependencia de entradas contiguas en una matriz (localidad espacial), se pueden asignar bloques para dividir los datos con mínimas comunicaciones.
#### Bloque
Se basa en dividir el espacio de datos en bloques que permitan a las tareas que consumen de los vecinos no tener que comunicar.
Principalmente dividiendo por:
- Vector, tareas que consumen sus vecinos en un vector se dividirá el vector en bloques unidimensionales.
- Filas, sobre matrices que consumen los vecinos de la fila son divididos en bloques de filas.
- Columnas, sobre matrices que consumen los vecinos de la columna son divididos en bloques de columnas.
El tamaño se calculara con:$$m_{b}=\frac{n}{p}$$
## Distribuciones
### Cíclica por bloques
En la decisión de los tamaños de bloque se hace un compromiso con mayor tamaño de bloque disminuido la comunicación y menor tamaño distribuyendo mejor la carga.
## Asignación
### Grafos de dependencia estática
#### Reducciones

![[Pasted image 20230425084319.png]]

Para agrupar estos tipos de arboles en procesos se usa árbol binario de orden k.

![[Pasted image 20230425084522.png]]

Este método permiten hacer la reducción de k datos en $log(k)$ pasos.
#### Reducción con replicación
En caso de querer reducir y dar a todos los procesos una copia del resultado.
Esto se puede conseguir con un proceso de combinación y posteriormente difusión con coste de $2log(k)$ pasos.
De manera más eficientemente se puede hacer con comunicación bidireccional, haciendo que todos los procesos hagan la reducción de su posición relativa.

![[Pasted image 20230425085506.png]]

Ejemplo de k = 8:

![[Pasted image 20230425085654.png]]

Esta estrategia de hipercubo nos lleva a un costo de $log(k)$ pasos.
## Asignación dinámica
Los esquemas dinámicos se aplican sobre sistemas donde el coste de tarea o el número de tareas están indeterminados, lo que lleva a trabajo extra en el proceso de asignación.
El acercamiento a este problema se basa en colecciones de tareas pendientes con dos opciones:
### Centralizado
Tenemos un proceso maestro con una colección de tareas que son asignada a los procesos esclavo, que devolverán resultados o subtareas al maestro.

![[Pasted image 20230425090529.png]]

Este acercamiento no es escalable y tiene gran requerimientos de comunicación.
Se pueden optimizar estos procesos con:
- Planificación por bloques, establecimiento de bloques de tareas asignables en lugar de tareas individuales.
- Subproblemas locales, los esclavos que generan subtareas mantienen subtareas para su propia ejecución y manda un conjunto de ellas al maestro.
- Captación anticipada, petición de trabajos por adelantado para solapar los tiempos de comunicación.
### Descentralizados
El modelo descentralizado se basa en que todos los procesos pueden asignar tareas, teniendo tes métodos de asignación de tareas:
- Receptor, el proceso que requiere trabajo solicita al resto.
- Emisor, el que tiene trabajos los ofrece.
- Mixto, dependiendo del estado del sistema se hace una combinación de los anteriores.

![[Pasted image 20230425091356.png]]

A la hora de seleccionar el proceso de con el que comunicarse se pueden tener dos acercamientos:
- Aleatorio
- Sondeo cíclico, cada proceso tiene su contador que indica el objetivo de la ultima comunicación que se actualizará cuando se de una denegación.
La terminación en este tipo de esquemas es complicada de determinar, necesitando comunicación de finalización:
- Cíclica, comunicar los procesos en anillo llevando un mensaje de fiscalización entre los procesos, pasándolo en una dirección.
#### Dijkstra
Algoritmo de terminación cíclico, establecemos un color para los procesos, cuando se manda un trabajo a un proceso de indice mayor. Cuando el token de terminación llega a un proceso de color negro cambia su propio cor a negro, pasando a ser un token no fiable, si el token llega blanco es que esta fiable y se puede terminar.

![[Pasted image 20230425092853.png]]
# Tags
#2- 
#2-2 
#cp 