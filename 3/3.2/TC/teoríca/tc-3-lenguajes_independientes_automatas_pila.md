# Gramáticas y lenguajes regulares
Una gramática regular es una colección de un conjunto de símbolos no terminales o variables (N), conjunto finito de símbolos terminales o alfabeto ($\sum$), un conjunto finito de producciones o reglas de reescritura (P) y un símbolo destacado de N, inicial de la gramática (S).
Una gramática regular se puede decir que es:
- Lineal por la izquierda, $A\rightarrow w B$
- Lineal por la derecha, $A\rightarrow B w$

# Gramáticas independientes de contexto
Las gramáticas independientes no constan de restricciones en forma a diferencia de las regulares con las formas lineales.
# Árboles de derivación y ambigüedad
Representación de una cadena sobre una gramática, mostrando las normas de la gramática activadas. Estos árboles se pueden usar para ver la ambigüedad de la gramática, iterando exclusivamente por la derecha y por la izquierda sobre una cadena, en caso de dar árboles distintos se trata de una gramática ambigua. Una gramática ambigua no implica que el lenguaje generado de ella lo sea.
# Simplificación de gramáticas independientes de contexto
# Propiedades de los lenguajes independientes del contexto
Una de las principales características es para una GIC con $|N|=x$ el camino más largo es de profundidad $x+1$.
## Lema del Bombeo
Dado un lenguaje L independiente del contexto:
1. Tomamos la cadena $z\in L$ tal que $|z|\ge k$.
2. Consideramos las descomposiciones de z en $uvwxy$, tales que: 
	1. $|vwx| \le k$
	2. $|v | + |x| > 0$
	3. $uv^{i}wx^{i}y\in L, \forall i \ge 0$.

Mediante este lema podemos demostrar que un dado lenguaje no es un LIC.
# Autómatas de pila
Un APN es una colección de siete elementos, $M=(Q, \Sigma, \Gamma, s, Z, F, \Delta)$
- $Q$, conjunto finito de estados.
- $\Sigma$, alfabeto de símbolos de entrada.
- $\Gamma$, alfabeto de símbolos de la pila.
- $s\in Q$, estado inicial del autómata.
- $Z\in \Gamma$, símbolo inicial de la pila.
- $F\subseteq Q$, conjunto de estados de aceptación.
- $\Delta$, Conjunto de funciones de transición.

Siempre se puede convertir una GIC en un APN tal que L(APN) = L(GIC).
# Forma Greibach
Forma en la cual todas las relaciones son del tipo "Terminal" seguido de un número arbitrario de "No Terminal".