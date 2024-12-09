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
Modelo para la descripción de la ejecución por proceso iterativo de pequeños pasos computacionales, formalizado con la sintaxis ($\lambda$-calculus):
$\Large\frac{antecedente}{consecuente}$
#### Big-step
Modelo en el cual se especifican pasos grandes para pasar directamente de una frase de código a una respuesta, haciendo uso de evaluación recursiva.
### Denotaciónal
La esencia del modelado denotaciónal es la idea de que el significado de una frase, el programa puede ser obtenido del significado de sus partes.
#### Estructura
- Álgebra sintáctica, parte que determina la sintaxis del lenguaje.
- Álgebra semántica, parte que modela el significado de las frases del programa, compuesta por dominios semánticos.
- Función de significado, mapeado de los elementos sintácticos con su significado semántico.
#### Dominios semánticos
El significado de un programa es obtenido por el mapeo de dominio de contexto a dominios de solución:
- Dominio de contexto, modelado de los estados intermedios del programa.
- Dominio de solución, representación de los posibles significados del programa.
#### Compositionality
Método que permite la interpretación del significado del conjunto es la composición del significado de las partes. Esto tiene las siguientes implicacion ,El significado del programa es inmutable a cambios de partes siempre y cuando tengan el mismo significado.
# Semántica operacional
# Semántica denotacional
# Semántica axiomatica