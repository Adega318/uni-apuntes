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
Para la creación de metricas permite la evaluación de dos tipos de sets de recuperaciones:
- Ranked.
- Unranked.

Las principales métricas para sistemas  son calculadas mediante una matriz de confusión de la relevancia.

|              | relevante | no relevante |
| ------------ | --------- | ------------ |
| relevante    | TP        | FP           | 
| no relevante |     Fn      |           TN   |
Las métricas son las siguientes:
- Recall, $R=\frac{TP}{TP+FN}$
- Precision, $P=\frac{TP}{TP+FP}$