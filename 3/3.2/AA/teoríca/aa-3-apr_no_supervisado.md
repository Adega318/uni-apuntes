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
- K-means++, mejora sobre el sistema de inicialización de contenidos, maximizando la distancia entre los datos para minimizar la posibilidad del colapso de los centroides en subóptimos.
- K-medoids, substituye los centroides por medoids, datos reales considerados los representativos de su cluster.

## Jerárquico
Sistema de clustering que construye un árbol o un dendograma a partir de los datos, teniendo dos tipos principales:
- Aglomerativo, comienza con los puntos como clusters individuales y agruparlos.
- Divisivo, todos los puntos en un cluster y extraer los diferentes.

Para la medición de distancias existen los siguientes métodos:
- Máxima, medida de la distancia máxima entre los puntos de dos clusters.
- Mínima, medida de la mínima distancia entre puntos de dos clusters.
- Promedio, media de distancia entre los puntos de dos clusters.
- Centroide, distancia entre los centros geométricos de dos clusters.
- Ward.

La principal ventada de la agrupación jerárquica es la capacidad de regulación de la granularidad en los resultados a coste de un alto requerimiento computacional de entrenamiento.
## DBSCAN
Algoritmo de clustering de densidad basado en la vecindad de los datos, formando clustes por la identificación de zonas de alta densidad de datos. El sistema es regulado por:
- eps (epsilon), distancia máxima de dos puntos para su consideración como vecinos.
- minPts, número mínimo de puntos necesarios para la formación de un cluster.

## GMM
Bajo la suposición de la procedencia de datos de una distribución gaussiana, dividiendo los datos en un número de distribuciones, para el ajuste del modelo tenemos los parámetros:
- $\mu_{k}$, centro de cada cluster.
- $\Sigma_{k}$, ancho de cada cluster.
- $\Pi_{k}$, tamaño de la función gausiana de cada cluster.

El proceso se basa en la inicialización de los parámetros en las distribuciones gaussianas con la asignación de probabilidad de pertenencia a las diferentes distribuciones.
# Reducción de dimensionalidad
Proceso para la representación de datos en un espacio de características más pequeño sin perder información.
Basándose en la generación de árboles y entrenamiento de los mismos tenemos:
- Random forest, los árboles son evaluados haciendo uso de las siguientes medias para la evaluación de las características:
	- Gini, disminución de la impureza en los nodos donde se hace uso de las características para la separación de datos.
	- Accuracy, perdida de precisión por la eliminación de una característica.
- XGBoost, para la medida de la importancia de las características, se hace uso de:
	- Peso, número de veces que un atributo pertenece a un árbol.
	- Ganancia, mejora a la predicción proporcionada por cada característica.
	- Cobertura, número de muestras afectadas por la característica.

# Asociación de reglas
Para la asociación de regalas la principal técnica es la **Apriori**, algoritmo de minería de datos utilizado para encontrar patrones frecuentes o reglas de asociación en grandes conjunto de datos transaccionales, funcionando mediante la generación y prueba de hipótesis sobre elementos frecuentes en los datos.
# Detección de anomalías
La detección de anomalías se basa en el supuesto de las instancias contienen determinada estructura. Para la detección de anomalías las principales técnicas son:
- K-NN,
- One-class
- Custering
- Autoencoders
- Local Outliner Factor
# Redes de neuronas artificiales no supervisadas