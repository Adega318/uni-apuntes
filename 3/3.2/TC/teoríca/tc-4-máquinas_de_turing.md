# Definiciones
Una máquina de turing consta de siete elementos:
- Q, conjunto finito de estados.
- $\sum$, alfabeto de simbolos de entrada.
- $\varGamma$, alfabeto de simbolos en la cinta.
- $s\in Q$, estado inicial.
- $B \in \varGamma$, símbolo blanco.
- $F\subseteq Q$, estados de aceptación.
- $\delta :Q\times\varGamma\rightarrow Q\times\varGamma\times\{L,R\}$, 