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
