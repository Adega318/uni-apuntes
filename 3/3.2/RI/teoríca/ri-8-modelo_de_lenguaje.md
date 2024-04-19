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
Para suavizar podemos:
- Additive, aplica un suavizado general.
$\large p(w|d)=\frac{c(w,d)+1}{|d|+|V|}$
- Referencia, en caso de no estar en el documento dar el valor de la probabilidad en REF, documento de referencia.
$\large\alpha_d=\frac{1-\sum_{w\in d}p(w|d)}{\sum_{v\notin d}p(w|REF)}$
$\large p(w|d)=\alpha_dp(w|REF)$
- Descuento absoluto, refuce una cantidad constante de todos los terminos.
$\large p(w|d)=\frac{max(c(w,d)-\delta , 0)+\delta |d|_u p(w|REF)}{|d|}$
- Jelinek-Mercer, usa un parametro lambda para ponderar la importancia de la coleción y el documento.
$\large p(w|d)=(1-\lambda)\frac{c(w,d)}{|d|}+\lambda p(w|REF)$
- Dirichlet,  
$\large p(w|d)=\frac{c(w,d)+\mu\frac{c(w,C)}{|C|}}{|d|+\mu}$