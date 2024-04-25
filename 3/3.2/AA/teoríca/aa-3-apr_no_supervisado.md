# Agrupación
Sistemas con la intención de agrupar datos por similitud, sin clasificarlos en clases, para ello se hace uso de:
- K-means, hace uso de la agrupación de datos en un número k de clusters minimizando las distancias euclídeas entre los puntos, teniendo problemas para datos con distribuciones no clusterizadas.
	- Distancia de Manhattan
	- Distancia de Mahalanobis
	- Distancia del coseno
- K-means++, mejora sobre el sistema de inicialización de contenidos, maximizando la distancia entre los datos para minimizar la posibilidad del colapso de los centroide en subóptimos.
- K-medoids, substituye los centroides por medoids, datos reales considerados los representativos de su cluster.
- Jerárquico