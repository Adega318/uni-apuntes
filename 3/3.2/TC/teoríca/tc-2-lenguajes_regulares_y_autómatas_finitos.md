# Autómata finito determinista (AFD)
Para trabajar sobre estados tenemos que tener en cuenta 5 elementos para su representación matemática:
- $Q$, conjunto finito de estados.
- $\sum$, es el alfabeto de los símbolos de entrada.
- $s\in Q$, es el estado inicial del autómata.
- $\delta:Q\times\sum\to Q$, función de transición entre estados en función de la entrada.
- $F\subsetq Q$

Una cadena se considera aceptada si estando en el estado inicial, la entrada de la cadena lleva al estado final. El lenguaje aceptado para un automata M:
$L(M)=\{w\in\sum^{*}| \delta(s,w)\in F\}$

(a U ba\*)\*

(b+ U a U b+)*