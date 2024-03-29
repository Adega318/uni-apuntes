# La neurona artificial
Las neuronas artificiales reciben las entradas por la regla de propagación, las suman y multiplican por su peso y se le suma el **bias** con su peso (función de activación), el valor de salida se pasa por el **neta** a la función de salida. 
$$Y_{i}=f(\sum_{j=1}^{m} (w_{ij}x_{j})+b_{i})$$![[Pasted image 20230320084934.png]]

Las conexiones las podemos clasificar en función de su peso como:
- excitadoras $w_{ij}>0$
- inhibitorias $w_{ij}<0$
- inexistentes $w_{ij}=0$

Por otro lado, él bisas determina la sensibilidad de una neurona para la activación.
# Adaline
El modelo Adaline es un modelo supervisado con corrección de errores, corrige mediante la reducción del error cuadrático medio (ECM).
## Regala delta (LMS)
La regla delta o también conocida como el descenso del gradiente, basando sé en la derivación del error y minimización de la pendiente de la derivada.
Para cada patrón k:$$Y_{k}=\sum_{j=0}^{m}w_{kj}\cdot x_{j}$$
Error cuadrático:$$E_{k}=\frac{1}{2}(d_{k}-Y_{k})^2$$
Error cuadrático medio:$$E=\frac{1}{2}\sum_{k=1}^{L}(d_{k}-Y_{k})^2$$
Para minimizar el error se derivará con respecto a w, obteniendo información para la minimización de la pendiente del gradiente.
### Proceso regla delta
1. Inicialización aleatoria de los pesos.

![[Pasted image 20230518153743.png]]

2. Se determina la dirección de la pendiente más pronunciada (uso de la derivada del error).

![[Pasted image 20230518153802.png]]

3. Se modifican los pesos para moverse ene dirección al fondo.

![[Pasted image 20230518153817.png]]

### Modificación de pesos
Modificación del peso j, para un patrón k, en el instante t (descenso del gradiente):$$w_{j}(t+1)=w_{j}(t)+\mu\cdot(d_{k}-Y_{k})\cdot x_{jk}$$
La tasa de aprendizaje "$\mu$" determina el tamaño de salto en el descenso, pudiendo causar problemas en su erróneo ajuste.

![[Pasted image 20230518154232.png]]

### Aplicaciones
La principal utilidad de Adaline es el procesado de señales, pudiendo ser cualquier problema de separación de único plano.
# Perceptrón

![[Pasted image 20230518160341.png]]

El Perceptrón es un sistema de separación lineal similar a Adaline, diferenciándose en la inclusión de una función de trasferencia y cambios en el entrenamiento.
## Aprendizaje
Algoritmo original:
1. Si está bien no lo toques.
2. Si la salida es incorrecta negativa, se le sumo la entrada.
3. Si la salida es incorrecta positiva, se le resto la entrada.

Versión con regla delta:$$w_{i}(t+1)=w_{i}(t)+\mu(d(t)-y(t))x_{i}(t)$$
Con este algoritmo para cualquier problema de separación lineal es solucionable.
## Perceptrón Multicapa

![[Pasted image 20230518161036.png]]

Al añadir múltiples perceptrones se pasa de hacer separaciones lineales a pudiendo hacer separaciones polinómicas, produce el efecto de caja negra sobre el funcionamiento interno de la red.

![[Pasted image 20230320174935.png]]

Arquitectura multicapa:
- Capa de entrada, neuronas que retransmiten las entradas a las capas ocultas.
- Capas ocultas, procesan la información y mandan a las de salida.
- Capa de salida, reciben los datos de salida, pudiendo normalizarlos.

## Funciones de transferencia
Las funciones de trasferencia cumplen la función de trasferencia cumple dos funciones distintas dependiendo de la capa en la que se empleen:
- Internas, las funciones de las capas internas deben ser no lineales ya que su función es evitar que la capa colapse en una única función lineal por suma de lineales.
- Salida, las funciones en las capas de salida dependen del problema a tratar siendo para problemas de regresión funciones lineales, clasificación logsig o lineal, ...

Algunos de los tipos de funciones son:
### Escalón
Usada en problemas de clasificación.

![[Pasted image 20230322104454.png]]

### Lineal y lineal mixta
Sirve para separar el espacio en dos regiones, estas no pueden ser usados en capas internas.

![[Pasted image 20230322104439.png]]

### Sigmoidal

![[Pasted image 20230322104852.png]]$$f(n)=\frac{1}{1+e^{-n}}$$
### Hiperbólica

![[Pasted image 20230322104903.png]]$$f(n)=\frac{2}{1+e^{-2n}}-1$$
### Tabla de funciones

![[Pasted image 20230518164959.png]]

## Aplicaciones
### Clasificación
Dependiendo de el numero de clases en los que clasificar se usara una salida binaria o una neurona por clase. Estas salidas son normalizadas usando la función softmax:
$$ŷ_{i}=\frac{e^{y_{i}}}{\sum_{j=1}^{c}e^{y_{j}}}$$
Una ultima opción es usar una única salida continua con segmentos de salida asociados a distintas clases.
### Predicción
Aplicación de  perdición del progreso de datos en el tiempo.
### Clustering
Agrupación de valores bajo un criterio sin la existencia de clases.
### Aproximación de curvas
### Regresión
Aplicaciones de transformación de una entrada a una salida (filtros, chats, ...).
### Control
Control de sistemas basándose en datos.
## Entrenamiento
Se entrena utilizando Backpropagation, que es el método de entreno de multicapas que generaliza la regla delta mediante el uso de la propagación del error.
### Notación
- $n$ : número de entradas de cada patrón  
- $h$ : número de capa oculta
- $o$ : capa de salida  
- $p$ : patrón  
- $j$ : PE j en la capa oculta h  
- $k$ : PE k en la capa de salida  
- $w_{ji}^{h}$ : conexión PE i (capa h-1) con PE j (capa h)  
- $i_{pj}^{h}$: salida PE j en la capa oculta h para el patrón p

### Calculo de la responsabilidad del error
El algoritmo de backpropagation permite el calculo de la responsabilidad del error final sobre cada capa y neurona, denotado por "$\delta_{pk}^o$" para la capa de salida y por "$\delta_{pj}^h$" para las capas ocultas.
El calculo de la responsabilidad del error de la capa de salida es:$$\delta_{pk}^o=\delta_{pk}f_k^{o\ \prime}(neta_{pk}^o)$$
En base a ese cálculo y al calculo de cada capa posterior se propaga la responsabilidad hacia atrás con la siguiente formula:$$\delta_{pj}^h=f_j^{h\ \prime}(neta_{pj}^h)\sum_{k}\delta_{pk}^o\ w_{kj}^o$$
El proceso de la propagación del error comenzaría por la capa de salida, calculando "$\delta_{pk}^o$" para cada neurona de la capa:

![[Pasted image 20230518181109.png]]
![[Pasted image 20230518181121.png]]

Con las responsabilidades del error y los pesos que relacionan cada neurona con las de su capa anterior se calculan las responsabilidades de la ultima capa oculta:

![[Pasted image 20230518181134.png]]
![[Pasted image 20230518181146.png]]

Se repetiría el proceso con cada capa oculta anterior hasta obtener todas las responsabilidades.
### Variación de pesos
En base a las responsabilidades de cada neurona y el error total se modifican los pesos usando el descenso del gradiente.
La capa de salida modifica los pesos mediante:$$w_{kj}^{o}(t+1)=w_{kj}^{o}(t)+\mu \delta_{pk}^{o}\ i_{pj}^{o-1}$$
Las capas ocultan se modificaran por:$$w_{ji}^{h}(t+1)=w_{ji}^{h}(t)+\mu \delta_{pj}^{h}\ i_{i}^{h-1}$$
### Entradas
La habilitación del entrenamiento se puede hacer separando las entradas, normalizar los datos, pudiendo ser normalizados por:
- máximo y mínimo, $X=\frac{x-min}{max-min}$
- desviación típica, $X=\frac{x-\mu}{\sigma}$

### Salidas
Para facilitar las salidas en necesaria su normalización y separación.
### Control de convergencia

![[Pasted image 20230426192320.png]]

Se ajusta la tasa de aprendizaje de manera que por el mismo salto en el mismo lado del mínimo se aumenta la tasa de aprendizaje, cuando se cambie de lado del mínimo se reduce.

![[Pasted image 20230518185648.png]]

## Sobre entrenamiento
El sobre entrenamiento es el resultado de el excesivo entrenamiento de un modelo con un conjunto de datos, reduciendo la capacidad de generalización de la red. Es cuando el modelo interpreta el ruido como una característica del conjunto.
### Prevención
Para la prevención del sobre entrenamiento tenemos varias técnicas disponibles:
- L1, usar los pesos en la función de coste
- L2, añadir f coste a la suma de cuadrado de valores de peso
- Parada temprana

Para evaluar el sobre entrenamiento y detectarlo el conjunto de datos se divide en tres categorías:
- Entrenamiento, conjunto de datos usado en el entrenamiento del sistema.
- Validación, conjunto usado para evaluar la calidad de la red (no produce cambios sobre la misma).
- Test, conjunto reservado para la evaluación final del sistema.

Para la evaluación del error se hace uso de el error de las pruebas del conjunto de validación, el aumento de este error indica el sobre entrenamiento.

![[Pasted image 20230518190606.png]]

Pasos en el entrenamiento para el sobre entrenamiento:
1. se entrena
2. se valida el error con un conjunto de validación, que no aprende.
3. Si se realizan más de un número de ciclos sin mejoras de error damos error.

# Tags
#2- 
#2-2 
#si