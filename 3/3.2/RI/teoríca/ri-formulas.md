# Ranking
# Evaluación
Para el cálculo de las métricas de evaluación se genera la matriz de confusión:

| r\p    | rel | no rel |
| ------ | --- | ------ |
| rel    | TP  | FN     |
| no rel | FP  | TN     |
$\large Recall =\frac{TP}{TP+FN}$
- $TP+FN$, número de documentos relevantes.
$\large Precision=\frac{TP}{TP+FP}$
- $TP+FP$ (K), número de documentos recuperados.
$\large AP=\frac{\sum_{k=i}P@k}{TP+FN}$
$\large F_{\beta}=(1+\beta^{2})\frac{Precision\times Recall}{\beta^{2}\times Precision+Recall}$
$\large DCG_{p}=rel_{1}+\sum\limits_{i=2}^{p}\frac{rel_{i}}{\log_{2}i}$
# Probabilidad
# Grafo web
$(1-\lambda)MTI+\frac{\lambda}{N}\times [1s]$
- N, número de páginas.
- [1s], matriz de unos de NxN.
- $\lambda$, valor de teleporting.
- MTI, matriz de conexión con la probabilidad repartida por filas.

Page

