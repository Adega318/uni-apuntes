La principal métrica de evaluación de la información recuperada es la satisfacción del usuario, la cual es representada por:
- Aumento en clics.
- Aumento en visitas o visitas recurrentes.
- Relevancia de resultado.

# Clásico
El acercamiento clásico a la evaluación se basa en tres elementos:
- Recogida de documentos.
- Set de documento calcificado correctamente.

## Relevancia de búsqueda
Relevancia de los resultados con respecto a la necesidad de información del usuario.
## Métrica de evaluación
Para la creación de métricas permite la evaluación de dos tipos de sets de recuperaciones:
- Ranked.
- Unranked.

Las principales métricas para sistemas puntuados son calculadas mediante una matriz de confusión de la relevancia.

|              | relevante | no relevante |
| ------------ | --------- | ------------ |
| relevante    | TP        | FP           |
| no relevante | FN        | TN           |
Las métricas son las siguientes:
- $Recall =\frac{TP}{TP+FN}$
	- $TP+FN$, número de documentos verdaderamente relevantes.
- $Precision=\frac{TP}{TP+FP}$
	- $TP+FP$, número de documentos recuperados.

Para mejorarlas se calcula:
- AP, media de las precisiones actualizadas con cada petición.
- Precision@K, precisión de los top k documentos.
- MRR, media de posición del primer documento relevante recuperado.
- $F_{\beta}=(1+\beta^{2})\frac{Precision\times Recall}{\beta^{2}\times Precision+Recall}$

La importancia de un documento se puede estipular de manera no binaria con la **ganancia acumulativa descontada**:
$\large DCG_{p}=rel_{1}+\sum\limits_{i=2}^{p}\frac{rel_{i}}{\log_{2}i}$
Este valor es normalmente normalizado con el DCG ideal a la posición.
## Significancia
Para la comparación de las métricas se debe calcular el p-valor lo cual indica la probabilidad de obtener valores extremos.
## Consistencia de ranking
Para medir la consistencia de las evaluaciones se hace uso del índice kappa:
$k=\frac{P(A)-P(E)}{1-P(E)}$
- P(A), probabilidad de acuerdo entre evaluaciones.
- P(E), probabilidad de acuerdo aleatorio.