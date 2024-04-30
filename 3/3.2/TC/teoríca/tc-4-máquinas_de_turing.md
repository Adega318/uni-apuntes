# Definiciones
Una máquina de turing consta de siete elementos:
- $Q$, conjunto finito de estados.
- $\Sigma$, alfabeto de símbolos de entrada.
- $\varGamma$, alfabeto de símbolos en la cinta.
- $s\in Q$, estado inicial.
- $B \in \varGamma$, símbolo blanco.
- $F\subseteq Q$, estados de aceptación.
- $\delta :Q\times\varGamma\rightarrow Q\times\varGamma\times\{L,R\}$, función de transición para la entrada y estado saliendo movimiento L o R. 

# Lenguajes y MT
El lenguaje aceptado por una MT es definido por:
$L(M)=\{w\in\sum^*|sw\vdash^*w_1pw_2\ donde\ p\in F \ w_1,w_2\in\varGamma^*\}$
Estas máquinas pueden leer y escribir sobre una cinta con la capacidad de moverse a la derecha e izquierda.
# Construcción de máquinas
Para simplificar la construcción de máquinas de Turing se establecen componentes básicas para la realización de tareas habituales:
- $R_{x}$ , se mueve hacia la derecha hasta encontrar un elemento x.
- $L_{x}$ , se mueve hacia la izquierda hasta encontrar un elemento x.
- $R_{}$