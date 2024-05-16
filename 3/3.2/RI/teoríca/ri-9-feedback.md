El objetivo del feedback es el mejorar la recuperación de información.
# VSM
Para el feedback en el modelo de espacio de vectores hacemos uso de los centroides de documentos, definidos por:
$\mu(D)=\frac{1}{|D|}\sum\limits_{d\in D}v(d)$
- D, conjunto de documentos.
- $v(d)$, vector que representa el documento d.

## Rocchio
El algoritmo de Rocchio permite optimizar para una query $q_{opt}$ que maximiza:
$q_{opt}=\mu(D_{r})+[\mu()]$