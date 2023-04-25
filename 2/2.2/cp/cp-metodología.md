# Descomposición de tareas
## Dominio
Técnica usada sobre grandes estructuras, consiste de dos pasos:
- Troceado de datos
- Asociación de la computación
### Regla del propietario
Los procesos dependientes de un conjuntos de datos es responsabilidad del propietario de esos datos, en caso de necesitar más datos no poseídos puede incumplirse.
## Funcional
Descompones las tareas de calculo del algoritmo en distintos procesos, esta descomposición dará a procesos con dependencias entre si.
## Recursiva
División del problema en procesos de manera recursiva con un criterio de parada para ejecución.
## Especulativa
La especulativa se da cuando puedes tomar un atajo que no funciona siempre y se prueba a hacerlo.
## Tareas
Se descompone el programa en tareas de árbol, cada tarea es independiente internamente, teniendo su propio estilo de descomposición.
Se pueden establecer las tareas de dos maneras:
- Estática, si tenemos un problema estable con iteraciones determinado podemos definir las tareas de manera permanente.
- Dinámica, se crean tareas en el código en función del progreso del programa.
## Asignación de tareas

# Asignación estática
## Descomposición de dominio
### Bloque
Se basa en dividir el espacio de datos en bloques que permitan a las tareas que consumen de los vecinos no tener que comunicar.
Principalmente dividiendo por:
- Vector, tareas que consumen sus vecinos en un vector se dividirá el vector en bloques unidimensionales.
- Filas, sobre matrices que consumen los vecinos de la fila son divididos en bloques de filas.
- Columnas, sobre matrices que consumen los vecinos de la columna son divididos en bloques de columnas.
El tamaño se calculara con:$$m_{b}=\frac{n}{p}$$
# Distribuciónes
## Cíclica por bloques
En la decisión de los tamaños de bloque se hace un compromiso con mayor tamaño de bloque disminuido la comunicación y menor tamaño distribuyendo mejor la carga.
# Asignación
## Grafos de dependencia estática
### Reducciones

![[Pasted image 20230425084319.png]]

Para agrupar estos tipos de arboles en procesos se usa árbol binario de orden k.

![[Pasted image 20230425084522.png]]

Este método permiten hacer la reducción de k datos en $log(k)$ pasos.
## Reducción con replicación
En caso de querer reducir y dar a todos los procesos una copia del resultado.
Esto se puede conseguir con un proceso de combinación y posteriormente difusión con coste de $2log(k)$ pasos.
De manera más eficientemente se puede hacer con comunicación bidirecional, haciendo que todos los procesos hagan la reducción de su posición relativa.

![[Pasted image 20230425085506.png]]

Ejemplo de k = 8:

![[Pasted image 20230425085654.png]]

Esta estrategia de hipercubo nos lleva a un costo de $log(k)$ pasos.
## Esquemas dinámicos
Los esquemas dinámicos se aplican sobre sistemas donde el coste de tarea o el número de tareas están indeterminados, lo que lleva a trabajo extra en el proceso de asignación.
El acercamiento a este problema se basa en colecciones de tareas pendientes con dos opciones:
### Centralizado
Tenemos un proceso maestro con una colección de tareas que son asignada a los procesos esclavo, que al terminar devuelven los resultados al maestro.
# Tags
#2- 
#2-2 
#cp 