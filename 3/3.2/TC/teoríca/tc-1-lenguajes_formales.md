# Alfabetos, palabras y lenguajes
Definimos un alfabeto como un conjunto no vacío y finito de símbolos. Con los símbolos de un alfabeto a un conjunto finito determinado de los mismos se denomina palabra y el conjunto de las mismas forma un lenguaje.
# Operaciones con palabras
- Para una palabra w su longitud se denota como |w|.
- Si w y z son palabras su concatenación es la palabra con sus símbolos, denotada por $w\cdot z$
- La potencia n-ésima de una palabra w es $w^{n}$
	- $\in\ \ si\ n=0$
	- $ww^{n-1}\ \ si\ n>0$
- La inversa de una palabra w es la palabra transpuesta.
- Un prefijo z de una palabra w es una palabra con los primeros caracteres de w, lo inverso es el sufijo, siempre que z y w sean distintos se dirá que son propios.
- Una subcadena es una porción interna de una palabra tal que z es una subcadena si existe $w=xzy$.

# Operaciones con lenguajes
- La concatenación de dos lenguajes A y B se define como $A\cdot B=\{w\cdot y|w\in A, y\in B\}$
- La n-ésima potencia de un lenguaje A es definida como $A^{n}$
	- $\{\in\}\ \ si \ n=0$
	- $A\cdot A^{n-1}\ \ si \ n>0$
- La unión e intersección de lenguajes son
	- $A\cup B=\{w|w\in A\ o\ w\in B\}$
	- $A\cap B= \{w|w\in A\ y\ w \in B\}$
- Para un lenguaje a su cierre de kleene
	- $A^{*}=\bigcup$