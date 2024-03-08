# Autómata finito determinista (AFD)
Para trabajar sobre estados tenemos que tener en cuenta 5 elementos para su representación matemática:
- $Q$, conjunto finito de estados.
- $\sum$, es el alfabeto de los símbolos de entrada.
- $s\in Q$, es el estado inicial del autómata.
- $\delta:Q\times\sum\to Q$, función de transición entre estados en función de la entrada.
- $F⊆ Q$, conjunto de estados finales o de aceptación.

Una cadena se considera aceptada si estando en el estado inicial, la entrada de la cadena lleva al estado final. El lenguaje aceptado para un autómata M:
$L(M)=\{w\in\sum^{*}| \delta(s,w)\in F\}$
# Autómata finito no determinista (AFN)
Autómatas que para una misma cadena puede tener varios resultados. Los no deterministas cambian su función de transición al dar un conjunto de estados en lugar de uno único.
Las transiciones paran a ser un paso de carácter a conjunto de estados, considerando la cadena como aceptada si alguno de los estados en el conjunto es un estado final.
# Equivalencias entre AFN y AFD
Tanto los autómatas deterministas como no deterministas pueden procesar los lenguajes reales, teniendo la distinción el no determinista al poder procesar los irreales.
# Autómata finito no determinista con transiciones épsilon (AFN-$\epsilon$)
Autómatas no determina con la capacidad de realizar transiciones con cadenas vacías, tomando el camino vacío antes de procesar ningún símbolo.
# Autómatas finitos y expresiones regulares
Para dos expresiones regulares se 