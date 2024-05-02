# Sintaxis y semantica
## Sintaxis
- $p$, un atomo
- $\top$, verdadero
- $\bot$, falso
- $¬\alpha$
- $\alpha\vee\beta$
- $\alpha\wedge\beta$
- $\alpha\rightarrow\beta$
- $\alpha\leftrightarrow\beta$
- $(\alpha)$

## Semantica
# Razonamiento proposicional
## SAT
Sistemas de resolución estandarizado de altas prestaciones, teniendo entrada en forma normal conjuntiva (CNF).
Para pasar a la normal conjuntiva:
1. Eliminar las implicaciones.
2. Negativa normal mediante la aplicación de De Morgan asta que los átomos sean los únicos negados.
3. Aplica la distributiva y asociativa para tener una conjunción de disyunciones.

# Razonamiento basado en reglas
Razonamiento donde se establecen reglas para obtener conclusiones, hay dos lecturas de reglas:
- Lanzamiento de reglas, si se activa el cuerpo se produce la cabeza (ASP).
- Objetivos, se considera el objetivo, cabeza, y se buscan sus causas, cuerpo (Prolog).

# Negación por defecto
# Programas estratificado
Programas que al realizar el grafo de dependencia no tiene ciclos con aristas negativas, siendo el grafo de dependencia el construido con los átomos como nodos y aristas como la relación de cabeza a cola de las reglas, siendo las aristas negativas cuando el elemento de la cola se haya negado.