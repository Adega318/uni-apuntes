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
- Vector, tareas que consumen sus vecinos en un vector se dividirá el vector en bloques unidimensionales, de tamaño $m_{b}=$.
- Filas
- Columnas
# Tags
#2- 
#2-2 
#cp 