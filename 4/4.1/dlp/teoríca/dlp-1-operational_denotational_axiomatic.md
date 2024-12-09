# Introducción
- Sintaxis, estructura y símbolos usados para la escritura en el lenguaje.
- Semántica, significado de la sintaxis del lenguaje:
	- Estática, validación de la sintaxis con sentido semántico correcto.
	- Dinámica, interpretación de la semántica válida.
# Semántica estática
Las gramáticas libres de contexto no son capaces de describir toda la sintaxis de los lenguajes de programación: 
- Libres de contexto (tipos, operadores, ...)
- No libres (variables, ...)
## Gramáticas de atributos
Gramáticas con cierta información semántica en el árbol de nodos, siendo computada:
- Atributos heredados son decorados de arriba a abajo.
- Atributos sintetizados son decorados de abajo a arriba.
# Semántica dinámica
## Especificación
### Operacional
Formalización de las instrucciones comunes de un programa que pueden ser seguidas en un proceso de aplicación de reglas.  Estas reglas también pueden describir como construcciones del lenguaje, afectan a máquinas abstractas, a cada estado de estas máquinas se le denota como configuración, estas máquinas están divididas en dos elementos:
- Código, frase del programa que controla la computación.
- Estado, entidades las cuales son manipuladas por el programa durante la ejecución.
#### Ejecución
Durante la ejecución se mapean el programa y sus entradas a una configuración inicial, sobre esta configuración se aplican iterativamente las reglas para obtener configuraciones intermedias de las cuales la última será mapeada a la salida el programa.
#### Terminación
La máquina puede no llegar a una configuración final, estas configuraciones a las que no se les puede aplicar reglas para continuar se llaman estados atascados, los cuales modelan situaciones de error.
#### Small-step
Modelo para la descripción de la ejecución por proceso iterativo de pequeños pasos computacionales, formalizado con la sintaxis:
$\Large\frac{antecedente}{consecuente}$
#### Big-se
# Semántica operacional
# Semántica denotacional
# Semántica axiomatica