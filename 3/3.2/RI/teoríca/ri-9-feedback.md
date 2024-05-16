El objetivo del feedback es el mejorar la recuperación de información.
# VSM
Para el feedback en el modelo de espacio de vectores hacemos uso de los centroides de documentos, definidos por:
$\mu(D)=\frac{1}{|D|}\sum\limits_{d\in D}v(d)$
- D, conjunto de documentos.
- $v(d)$, vector que representa el documento d.

## Rocchio
El algoritmo de Rocchio permite optimizar para una query $q_{opt}$ que maximiza:
$q_{opt}=\mu(D_{r})+[\mu(D_{r})-\mu(D_{nr})]$
- $D_{r}$, conjunto de documentos relevantes.
- $D_{nr}$, conjunto de documentos no significativos.

Donde la query obtenida es la óptima para la obtención de los documentos relevantes.
## Pseudo relevancia
La obtención de feedback específico tiene difícil obtención por ello se hace uso de la pseudo relevancia, donde se obtiene de manera automática juicios de relevancia del usuario, siendo bueno en promedio.
# RM
