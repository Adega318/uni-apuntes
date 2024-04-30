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
Una de las principales caracteristicas de los len Para una GIC con $|N|=x$ el camino más largo es de profundidad $x+1$.

# Autómatas de pila
Autómatas con cierta capacidad de memoria implementada mediante el  uso de una pila, tomando como necesidades para las transiciones entradas y cima de la pila.
# Forma Greibach
Forma en la que toda relación termina en "No terminal".