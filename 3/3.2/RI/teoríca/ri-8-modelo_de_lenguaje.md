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