Los modelos probabilísticos se basan en la probabilidad de relevancia de los diferentes documentos para una query dada. Para ello tenemos tres principales variables:
- Q, query dada.
- D, documento en el sistema.
- R $\in [0,1]$, relevancia de un documento D para la query Q.

# Condicionales
De esta manera tenemos la ecuación $P(R|Q,D)$ que nos da la probabilidad de una relevancia dada una query y documento donde el objetivo es la probabilidad para la máxima relevancia $P(R=1|Q,D)$, para ello calculamos $P(R=1|Q,D)=g(rep(Q,D),\theta)$ donde $rep(Q,D)$ es la relevancia calculada y $\theta$ información de entrenamiento.
Las principales métricas de ranking son:
- Frecuencia media absoluta de query, $X_{1}=\frac{1}{M}\sum\limits_{1}^{M}\log QAF$
- Longitud de query, $X_{2}=\sqrt{QL}$
- Frecuencia media absoluta de documento, $X_{3}=\frac{1}{M}\sum\limits_{1}^{M}\log DAF$
- Longitud de documento, $X_{4}=\sqrt{DL}$
- Frecuencia inversa de documento, $X_{5}=\frac{1}{M}\sum\limits_{1}^{M}\log\frac{N-n_{t}}{n_{t}}$
- Número de términos comunes, $X_{6}= \log M$

## Puntuación por regresión
Para clasificar se puede hacer uso de regresiones, entre las cuales tenemos:
- Lineal, relación entre un escalar dependiente y una o más explicativos.
- Logística, $P(R=1|Q,D)=\sigma(w^{T}X)=\frac{1}{1+exp(-w^{T}X)}$

## Ventajas y desventajas
Las principales ventajas son el uso de la probabilidad, absoluto de relevancia, con el problema del desempeño dependiente de las características seleccionadas.
# Generativos
El modelo generativo se basa en la generación de:
$Odd(R=1|Q,D)=\frac{P(Q,D|R=1)P(R=1)}{P(Q,D|R=0)P(R=0)}$
Este modelo hace la suposición de la relevancia como una variable binaria, teniendo dos variantes:
- Document generation, $P(Q,D|R)=P(D|Q,R)P(Q|R)$
- Query generation, $P(Q,D|R)=P(Q|D,R)P(D|R)$

## Document generation
$Odd(R=1|Q,D)=\prod\limits_{i=1}^{k}\frac{P(A_{i}=d_{i}|Q,R=1)}{P(A_{i}=d_{i}|Q,R=0)}$
Con este modelo se hace la presuposición que los términos no presentes en la query son equiprobables.
## Robertson-Sparck Jones (RSJ)
$p_{i}=P(A_{i}=1|Q,R=1)$, probabilidad de aparición de $A_{i}$ en un documento relevante.
$u_{i}=P(A_{i}=1|Q,R=0)$, probabilidad de aparición de $A_{i}$ en un documento no significativo.
Se pueden estimar estos dos variables como:
- $p_{i}\simeq\frac{(rel.doc\ with\ A_{i})+0.5}{(rel.doc)+1}$
- $u_{i}\simeq\frac{(nonrel.doc\ with\ A_{i})+0.5}{(nonrel.doc)+1}$

## Estimación de parámetros
Para la estimación de parámetros podemos hacer uso de múltiples acercamientos.
- Probabilidad máxima, toma el valor con mayor probabilidad.
- Bayesiano, mejor consistente con nuestro conocimiento previo.
