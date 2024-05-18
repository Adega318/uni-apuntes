# Ranking
Term frequency
$raw\ tf(t,d)=f(t,d)$
- $f(t,d)$, frecuencia del término en el conjunto de documentos d.

Inverse document frequency
$idf(t)=1+log(\frac{N}{df(t)})$
- N, número de documentos.
- $df(t)$, número de documentos conteniendo t.

# Similaridad
Para el calculo de la similaridaz se hace:
| term | idf | Query weights | Raw tf | Raw tf x idf | Doc weights |
| ---- | --- | ------------- | ------ | ------------ | ----------- |
| t    | $N/df(t)$    |  $idf\times in(t,q)$ |        |              |             |
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

$\large MAP=\frac{\sum\limits_{i=1}^{n}AP_{qi}}{n}$

$\large F_{\beta}=(1+\beta^{2})\frac{Precision\times Recall}{\beta^{2}\times Precision+Recall}$

$\large DCG@p=rel_{1}+\sum\limits_{i=2}^{p}\frac{rel_{i}}{\log_{2}i}$

$\large NDCG@p=\frac{DCG@p}{DCG@p(for\ ideal\ rank)}$
# Probabilidad
Probabilidad de query.
$\large P(q|d)=\Pi_{i}(1-\lambda)\frac{f_{q_{i}},d}{|d|}+\lambda\frac{f_{q_{i}},C}{|C|}$
- $f_{w},d$, frecuencia de la palabra w en el documento d.
- C, conjunto de todos los documentos.
- $\lambda$, valor de suavizado Jelinek-Mercer.

Probabilidad a Priori
$\large P(d|q)=P(q|d)\frac{P(d)}{P(q)}=_{rank}P(q|d)P(d)$
# Feedback
$\large \mu(D)=\frac{1}{|D|}\sum\limits_{d\in D}v(d)$
- D, conjunto de documentos.
- $v(d)$, vector que representa el documento d.

$\large q_{opt}=\mu(D_{r})+[\mu(D_{r})-\mu(D_{nr})]$
- $D_{r}$, conjunto de documentos relevantes.
- $D_{nr}$, conjunto de documentos no significativos.

$\large q_{m}=\alpha q_{0}+\beta\mu(D_{r})-\gamma\mu(D_{nr})$
- $q_{0}$, query original

```note!
no puede tener valores negativos, se substituyen por 0
```
# Grafo web
Matriz de transición de grafo web
$MTI_{\lambda}=(1-\lambda)MTI+\frac{\lambda}{N}\times [1s]$
- N, número de páginas.
- [1s], matriz de unos de NxN.
- $\lambda$, valor de teleporting.
- MTI, matriz de conexión con la probabilidad repartida por filas.

Page rank
$p_{t}(d)=p_{t-1}(d)MTI_{\lambda}$