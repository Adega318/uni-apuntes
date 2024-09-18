# Notación de chomsky
NTPS:
- N, no terminales, los cuales pueden ser substituidos por otros no terminales.
- T, terminales, símbolos finales.
- P, reglas, conjunto de reglas.
- S, axioma, elemento no terminal de comienzo del sistema.

# Clasificación de chomsky
Chomsky divide las gramáticas en cuatro tipos:
## Tipo 0
Estructura de frase
$\alpha \rightarrow \beta$
$\alpha \in (NUT)^+$
$\beta \in (NUT)^*$
Donde la única restricción es que $\alpha$ nunca puede ser vacío.
## Tipo 1
Con contexto 
$\alpha A\beta \rightarrow \alpha v\beta$
$\alpha,\beta \in (NUT)^*$
$v \in (NUT)^+$
$A \in N$