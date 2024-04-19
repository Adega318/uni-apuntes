# Distribucción de palabras
# Modelo de lenguaje unigram
Se supone que las palabras son independientes:
$p(w_1...w_n)= p(w_1)...p(w_n)$
Esto simplifica enormemente los calculos.

P(D1|Q) > P(D2|Q) > P(D3|Q) ?
en caso de cumplirse podemos hacer el ranking
D1, D2, D3

P(D|Q) = P(D/\\Q)/P(Q)
P(Q|D) = P(D/\\Q)/P(D)
P(D|Q)P(Q)=P(Q|D)P(D)
siendo P(Q|D) el query likihod

Podemos establecer la probabilidad de un documento en función de la query como:
$P(D|Q)=P(Q|D)P(D)$

Para estimar la probabilidad de un documento se puede usar una equitativa entre todos los documentos o algun tipo de metrica de calidad.

Para estimar la probabilidad de la query en base al documento como:
$Q_i$, termino numero i de la query.
$\log p(Q|D)=\displaystyle\sum_i \log p(Q_i|D)$
Para optener la probabilidad de un termino en un documento se hace uso de la división del tf del termino y el número de terminos del documento, esto se le hace llamado estimación MLE, teniendo el probelma de la perdida de los sinonimos y relaciones sintacticas, para evitar esto se hace uso de tecnicas de smoothing.

## Smoothing
A las palabras con probabilidad 0 en el documento se le aplica cierta probabilidad para así redistribuir las probabilidades evitando las 0.
