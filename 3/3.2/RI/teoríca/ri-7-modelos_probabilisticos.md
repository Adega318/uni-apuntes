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
Las principales ventajas son el uado de la probabilidad, absoluto de relevancia con el problema del desempeño dependiente de las caracteristicas selecionadas.