Los sistemas de aprendizaje no supervisado permite el entrenamiento sobre grandes cantidades de datos no etiquetados, teniendo grandes dificultades para la evaluación de los resultados del entrenamiento.
La principal función de los sistemas no supervisados es la agrupación de instancias similares, sin clasificarlos en clases.
# Clustering
Método de agrupación mediante la medida de la similitud de datos.
## K-means
Los métodos de K-means usan distancias entre los puntos para su agrupación, usando principalmente las distancias euclidianas y teniendo problemas con datos no clusterizables y sensibilidad a la inicialización de los clusters.
Otras métricas de distancia son:
- Distancia de Manhattan, suma de las diferencias absolutas entre las coordenadas de los puntos.
- Distancia de Mahalanobis, distancia con consideración de la escala de las variables.
- Distancia del coseno, medición de la similitud angular entre dos vectores de características.

Algunas variantes de K-means son:
- K-means++, mejora sobre el sistema de inicialización de contenidos, maximizando la distancia entre los datos para minimizar la posibilidad del colapso de los centroide en subóptimos.
- K-medoids, substituye los centroides por medoids, datos reales considerados los representativos de su cluster.


- Clustering jerárquico, división de los datos en grupos anidados mediante la agregación o división de grupos existentes.
- DBSCAN, agrupación de puntos por densidad de puntos cercanos.
- GMM, asignación de probabilidades a los datos para su pertenencia a diferentes grupos.


- Reducción de dimensionalidad.
- Asociación de reglas.
	- Apriori
- Detección de anomalías.
	- K-NN
	- One-class
		- SVM
		- Isolation forest
- Redes de neuronas artificiales no supervisados.
	- Mapas autoorganizativos
	- Autoencoders



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
