Los modelos probabilísticos se basan en la probabilidad de relevancia de los diferentes documentos para una query dada. Para ello tenemos tres principales variables:
- Q, query dada.
- D, documento en el sistema.
- R $\in [0,1]$, relevancia de un documento D para la query Q.

De esta manera tenemos la ecuación $P(R|Q,D)$ que nos da la probabilidad de una relevancia dada una query y documento donde el objetivo es la probabilidad para la máxima relevancia $P(R=1|Q,D)$, para ello calculamos $P(R=1|Q,D)=g(rep(Q,D),\theta)$ donde $rep(Q,D)$ es la relevancia calculada y $\theta$ información de entrenamiento.