# La neurona artificial
Las neuronas artificiales suman las entradas multiplicadas por su peso y el **bias** con su peso, el valor de salida se pasa por el **neta** a la función de salida. 
$$Y_{i}=f(\sum_{j=1}^{m} w_{ij}x_{j}+b_{i})$$![[Pasted image 20230320084934.png]]
Las conexiones las podemos clasificar en función de su peso como:
- excitadoras $w_{ij}>0$
- inhibitorias $w_{ij}<0$
- inexistentes $w_{ij}=0$
Por otro lado, él bisas determina la sensibilidad de una neurona para la activación.
# Adaline
El modelo Adaline es un modelo supervisado con corrección de errores, corrige mediante la reducción del error cuadrático medio (ECM).
## Regala delta (LMS)
La regla delta o también conocida como el descenso del gradiente, basando sé en la derivación del error y minimización de la pendiente de la derivada.
Para cada patrón k:
$$Y_{k}=\sum_{j=0}^{m}w_{kj}x_{j}$$
Error cuadrático:
$$E_{k}=\frac{1}{2}(d_{k}-Y_{k})^2$$
Error cuadrático medio:
$$E=\sum_{k=1}^{L}E_{k}=\frac{1}{2}\sum_{k=1}^{L}(d_{k}-Y_{k})^2$$
Para minimizar el error se derivará con respecto a w, obteniendo información para la minimización de la pendiente del gradiente.
### Modificación de pesos
Modificación del peso j, para un patrón k, en t:
$$w_{j}(t+1)=w_{t}+\mu(d_{k}-Y_{k})x_{jk}$$
$\mu:$ tasa de aprendizaje
# Perceptrón
Es el adaline, pero implementando una función de trasferencia para normalizar la salida.
Un perceptrón implementa un sistema de separación de conjuntos lineal.
## Estructura y aprendizaje
Algoritmo original:
1. Si está bien no lo toques.
2. Si la salida es incorrecta negativa, le sumo la entrada.
3. Si la salida es incorrecta positiva, le resto la entrada.
Luego se pasó a usar la regla delta:
$$w_{i}(t+1)=w_{i}(t)+\mu(d(t)-y(t))x_{i}(t)$$
### Multicapa
Al añadir múltiples perceptrones se pasó de hacer separaciones lineales a poder hacer separaciones polinómicas. También produce el efecto de caja negra sobre el funcionamiento interno de la red.
![[Pasted image 20230320174935.png]]
Arquitectura multicapa:
- Capa de entrada, neuronas que retransmiten las entradas a las capas ocultas.
- Capas ocultas, procesan la información y mandan a las de salida.
- Capa de salida, reciben los datos de salida.
## Funciones de transferencia
### Escalón
![[Pasted image 20230322104454.png]]
### Lineal y lineal mixta
Sirve para separar el espacio en dos regiones, estas no pueden ser usados en capas internas.
![[Pasted image 20230322104439.png]]
### Sigmoidal
![[Pasted image 20230322104852.png]]
$$f(n)=\frac{1}{1+e^{-n}}$$
### Hiperbólica
![[Pasted image 20230322104903.png]]
$$f(n)=\frac{2}{1+e^{-2n}}-1$$
## Entrenamiento y Aplicaciones
Las redes neuronales son aproximaciones universales, siendo garantizado su validez para cualquier problema asegurado por el teorema de la aproximación universal.
### Aplicaciones
- Ajuste de funciones y curvas
- Clasificación
- Regresión
### Entrenamiento
Se entrena utilizando Backpropagation, que es el método de entreno de multicapas que generaliza la regla delta mediante el uso de la propagación del error.
#### Notación
- $n$ : número de entradas de cada patrón  
- $h$ : capa oculta; 
- $o$ : capa de salida  
- $p$ : patrón  
- $j$ : PE j en la capa oculta h  
- $k$ : PE k en la capa de salida  
- $w_{pj}^{h}$ : conexión PE i (capa h-1) con PE j (capa h)  
- $i_{pj}^{h}$: salida PE j en la capa oculta h para el patrón p  
- $o_{pj}$ : salida PE j en la capa de salida para el patrón p
#### Error y pesos
Error de la capa oculta h:
$$\delta_{pj}^{h}=f_{j}^{h\prime}(neta_{pj}^{h})\sum\delta_{pk}^{o}w_{kj}^{o}$$
Corrección de la capa de oculta:
$$w_{ji}^{h}(t+1)=w_{ji}^{h}(t)+\mu \delta_{pj}^{h} i_{i}^{h-1}$$
Error de la capa de salida o:
$$\delta_{pj}^{o}=\delta_{pk}f_{j}^{o\prime}(neta_{pj}^{o})$$
Corrección de la capa de salida:
$$w_{kj}^{o}(t+1)=w_{kj}^{o}(t)+\mu \delta_{pk}^{o} i_{pj}^{o-1}$$
#### Proceso
1. Pesos iniciales aleatorios
2. Entrenamiento con un conjunto representativo.
3. Corrección de los pesos.
#### Entradas
La habilitación del entrenamiento se puede hacer separando las entradas, normalizar los datos, pudiendo ser normalizados por:
- máximo y mínimo, $X=\frac{x-min}{max-min}$
- desviación típica, $X=\frac{x-\mu}{\sigma}$
#### Salidas
Para facilitar las salidas en necesaria su normalización y separación.
#### Control de convergencia
Se ajusta la tasa de aprendizaje de manera que por el mismo salto en el mismo lado del mínimo se aumenta la tasa de aprendizaje, cuando se cambie de lado del mínimo se reduce.
#### Sobre entrenamiento
El sobre entrenamiento es el resultado de el excesivo entrenamiento de un modelo con un conjunto de datos, reduciendo la capacidad de generalización de la red. Es cuando el modelo interpreta el ruido como una característica del conjunto.
Para reducir los efectos del mismos:
- L1, usar los pesos en la función de coste
- L2, añadir f coste a la suma de cuadrado de valores de peso
- Parada temprana
Pasos en el entrenamiento para el sobre entrenamiento:
1. se entrena
2. se valida el error con un conjunto de validación, que no aprende, cuando su capitidisminuya se empieza a desajustar,
3. Si se realizan más de un número de ciclos sin mejoras de error damos error.
### Aplicaciones
#### Clasificación
Dependiendo de el numero de clases en los que clasificar se usara una salida binaria o una neurona por clase. Estas salidas son normalizadas usando la función softmax:
$$ŷ_{i}=\frac{e^{y_{i}}}{\sum_{j=1}^{c}e^{y_{j}}}$$
Una ultima opción es usar una única salida continua con segmentos de salida asociados a distintas clases.
#### Predicción
Aplicación de  perdición del progreso de datos en el tiempo.
#### Clustering
Agrupación de valores bajo un criterio sin la existencia de clases.
#### Aproximación de curvas
#### Regresión
Aplicaciones de transformación de una entrada a una salida (filtros, chats, ...).
#### Control
Control de sistemas basándose en datos.
# Tags
#2- 
#2-2 
#si