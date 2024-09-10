# Introducción
- Syntax, estructura del código.
- Semantics, sentido del código.
	- Static, validez del programa antes de ser ejecutado.
	- Dynamic, validez de la interpretación.
- Pragmatica

# Semántica
La semántica define lo que hace un dado programa.
## Métodos de especificación
No existen métodos oficiales para la especificación de la semántica:
- Operacional, aplicación mecánica de instrucciones predeterminadas modelando el hardware como una máquina abstracta.
- Denotación
- Axiomática

### Operacional
#### Smal step
Avance de principio a fin, parando al llegar a  fin o al llegar a un camino sin salida, lo que lanza errores.
- Componentes de código, frases que controlan el resto de la computación.
- Componentes de estado, entradas modificadas por el programa durante la ejecución.

#### Big step
El paso grande parte la tarea a la mitad para la posterior evaluación de las componentes, teniendo problemas con la parada por error.
