# Agrupación
Sistemas con la intención de agrupar datos por similitud, sin clasificarlos en clases, para ello se hace uso de:
- K-means, hace uso de la agrupación de datos en un número k de clusters minimizando las distancias euclídeas entre los puntos, teniendo problemas para datos con distribuciones no clusterizadas.
	- Distancia de Manhattan
	- Distancia de Mahalanobis
	- Distancia del coseno
- K-means++, mejora sobre el sistema de inicialización de contenidos, maximizando la distancia entre los datos para minimizar la posibilidad del colapso de los centroide en subóptimos.
- K-medoids, substituye los centroides por medoids, datos reales considerados los representativos de su cluster.
- Jerárquico, clustering que se basa en el establecimiento de un árbol, siendo considerablemente costoso y sensible al ruido.
	- Aglomerativo, comienza con los puntos como clusters individuales y agruparlos.
	- Divisivo, todos los puntos en un cluster y extraer los diferentes.
- DBSCAN, algoritmo de vecindad que crea cluster cuando se supera un número de vecinos determinados, siendo los puntos con suficientes vecinos considerados core.
- GMM, intenta repartir los datos en dos distribuciones gausianas.

# Reducción de dimensionalidad
Técnicas para la reducción de datos manteniendo la máxima cantidad de datos.
- Random Forest y GBoost, técnica supervisada para la clasificación y regresión que puntúa las características, lo que permite la extracción de características.
# Asociación de reglas
