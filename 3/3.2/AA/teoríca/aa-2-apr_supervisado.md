# Introducción
En el aprendizaje buscamos que el sistema generalice el conocimiento para permitir su funcionamiento sobre nuevos datos.
Para lo siguiente debemos distinguir entre parámetros e hiperparámetros:
- Parámetros, valores que definen el comportamiento del modelo.
- Hiperparámetros, parámetros definidos para el control del proceso de aprendizaje.

Por otra parte, se debe de controlar el sobre ajuste e infra ajuste, para ello se debe controlar la complejidad del modelo, tratando de llegar a una buena generalización, evitando el ajuste excesivo a los datos de entrenamiento. Otros aspectos ajustables son el número de ejemplos disponibles y error de generalización.
## Vapnik-Chervonenkis (VC)
La formalización de todo lo anterior se ve en la teoría de la dimensión Vapnik-Chervonenkis, esta teoría nos permite calcular la complejidad para un número de datos en una dimensión determinada.
Por esta teoría podemos calcular la relación entre el error del conjunto de entrenamiento y de test.

$\Large cota(e_{test}(f))=error_{train}+\sqrt{\frac{h(\log\frac{2n}{h}+1)-\log \frac{n}{4}}{n}}$

- h es la dimensión VC de f
- n es el número de ejemplos de entrenamiento
- n>h

## Errores en el entrenamiento
Tenemos dos tipos de errores en nuestros modelos, los irreducibles y los variables, los variables pueden ser reducidos:
- Bias.
	- Diferencia entre el valor medio predicho por el modelo y el valor medio real.
	- Indicando la posible falta de complejidad del sistema.
- Variance.
	- Entrenamiento del modelo sobre un subconjunto de los datos para observar la diferencia con el entrenado con el completo.
	- Es un buen indicador de oberfiting.

Para reducir estos errores podemos usar varias técnicas:
- Regularización.
	- Reduce la varianza a costa de un alto sesgo.
	- Reduce la complejidad usada de la red, permitiendo menor ajuste.

## Preporcesado de datos
Proceso de mejorar la calidad de los datos del dataset para potenciar las características interesantes para el entrañamiento del sistema, mediante el uso de transformaciones.
### Limpieza de datos
- Datos nulos.
	- Eliminación de la tupla.
	- Rellenar con datos a mano.
	- Usar una variable unknown.
	- Usar la media del atributo en el dataset.
	- Usar predicción para rellenar el dato.
- Datos con ruido.
	- Binning, se dividen los datos en una serie de bins a los que se calcula su media y se le da a todos los elementos el mismo valor.
	- Clustering, se agrupan los datos similares en grupos, permitiendo eliminar los datos fuera de rango.
	- Regresión, se crea una recta que se ajusta a los datos.
- Normalización, creación de una escala general para facilitar el aprendizaje.
	- Min/max, sé plasman los valores en un rango. $\Large v'=\frac{v-min}{max-min}(nuevomax-nuevomin)+nuevomin$
	- Escalado decimal, sé mueve el punto decimal en los valores del atributo.  $\Large v'=\frac{v}{10^{j}}$
	- Media cero, normalización para datos con algún dato fuera de lo normal. $\Large v'=\frac{v-\mu}{\sigma}$
- Agregación, unión de atributos basándonos en el conocimiento del problema.
- Generalización, sustitución de datos precisos por datos más abstractos y sencillos.

### Reducción de datos
- Análisis de componentes principales (PCA)
- Análisis de componentes independientes (ICA), técnica para obtener las fuentes originales sin datos extra.

## Evaluación de sistemas
Para evaluar clasificadores usamos una tabla de confusión donde se cuenta el número de veces que la predicción y la realidad coinciden o difieren.

|        | Predicción N | Predicción P |
| ------ | ------------ | ------------ |
| Real N | VN           | FP           |
| Real P | FN           | VP           |

- $VPP=\frac{VP}{VP+VF}$
- $VPN=\frac{VN}{VN+FN}$
- $\Large F_{1}=2(\frac{recall \times precision}{recall + precision})$

Para aplicar estas métricas a clasificaciones con múltiples opciones, la matriz de confusión será dividida usando la técnica de uno contra todos y se calcularán las métricas, siendo combinadas de una de las siguientes maneras:
- Macro, media de las métricas.
- Weighted, media ponderada para tener en cuenta datasets desbalanceados.
- Micro, aplicable para clases no excluyentes.

Otros criterios en clasificación son:
- Curva ROC, curva donde la **x** es la tasa de falsos positivos e **y** la de verdaderos positivos; esta curva se puede modificar usando el umbral en la salida.
- Índice Kappa, permite determinar hasta qué punto la concordancia observada es superior a la que se espera obtener por puro azar:

| A\B      | Negativo | Positivo |
| -------- | -------- | -------- |
| Negativo | a        | b        |
| Positivo | c        | d        |

$\Large P_{e}= \frac{(a+b)\times(a+c)+(c+d)\times(b+d)}{n^{2}}$
$\Large P_{0}= \frac{a+d}{n}$
$\Large K=\frac{P_{0}-P_{e}}{1-P_{e}}$
# Regresión logística
Método de modelación de relación entre características y probabilidad de pertenencia a una clase, para ello usamos el odds, siendo:

$\Large odds=\frac{p}{1-p}$

Donde **p** es la probabilidad de pertenecer a una clase concreta, esto nos permite conocer la probabilidad de que un elemento pertenezca a la clase.
Para hacer uso del odds, tomamos su logaritmo que lo llamamos logit:

$\Large logit(p)=\log(\frac{p}{1-p})=z$

Usando logit podemos despejar p:

$\Large p=\frac{1}{1+e^{-z}}$

Siendo una aproximación lineal al modelo, con facilidad de entrenamiento y configuración.
Por otra parte, la alternativa logística expresada como:

$\Large p=\frac{1}{1+e^{-(b_{0}+\sum b_{i}x_{i})}}$

Con las ventajas de mejorar la resiliencia a datos anómalos por la normalización aplicada entre 0 y 1.
## Entrenamiento
Para el entrenamiento se usan técnicas similares a las empleadas en los perceptrones, siendo la maximización de la verosimilitud de las conclusiones.
Siendo la maximización para **n** observaciones:

$LL = \sum [y\times log(p)+(1-y)\times log(1-p)]$

Aplicándole una técnica de ascenso del gradiante, siendo la técnica de descenso del gradiante con el signo inverso.
## Regularización
Proceso de refinado de datos para su consumo eficiente por el sistema.
### Lasso (L1)
Técnica que agrega a la función de coste un término de penalización que es proporcional al valor absoluto de los coeficientes, reduce los valores llevándolos a 0, consiguiendo en algunos casos anular parámetros, este parámetro de penalización es denotado por **$\lambda$**(lambda).
### Ridge (L2)
Similar a **L1** pero usando los coeficientes al cuadrado, reduciendo los coeficientes sin llevarlos a 0, aumentando la estabilidad pero evitando su eliminación.
### Elastic Net
Modelo que usa en combinación L1 y L2, pudiendo implementar regulación de implicación de cada una.
### Tikhonov
Para un problema de regresión lineal se añade una matriz $\Gamma$ para intentar encontrar una solución con normas bajas (Ridge es un caso particular de esta).
### Norma Max
Establecimiento de un valor máximo para los parámetros.
### Dropout
Técnica de desactivación de parámetros cuando se vuelven demasiado importantes.
### Parada temprana
Técnica basada en parar el entrenamiento iterativo de manera temprana para evitar el sobre ajuste.
# Máquinas de vectores de soporte (SVM)
Sistema de clasificación binaria (-1, 1) similar a un perceptron.
## Problemas linealmente separables
Para resolver problemas linealmente separables se define un hiperplano y sus positivos y negativos (márgenes), maximizando la distancia de los márgenes al hiperplano, siendo los datos sobre el margen los vectores de soporte.
## Problemas no linealmente separables
Para clasificar se debe de permitir cierta holgura y fallo. Permitimos fallos en la clasificación en la zona de margen del hiperplano, teniendo el parámetro C para elegir la prioridad de los márgenes sobre la holgura, maximizando el valor de $\alpha$:
- $0<\alpha<C$, elementos en el vector de soporte.
- $\alpha = 0$, elementos a mayor distancia que el vector de soporte.
- $\alpha=C$, elementos en la zona de holgura.

En caso de no querer considerar error se proyecta los datos en un hiperespacio para poder usar un hiperplano para separar los datos. Para construir este plano se hace uso del truco del kernel, donde se crea una función que transforma nuestros vectores en su proyección, permitiéndonos usar varios tipos de kernels para realizar esta función. Los kernels más comunes son:
- Lineal.
- Polinómico, adecuados para problemas sobre datos normalizados.
- Gausiano.
- Exponencial.
- Laplaciano, equivalente a exponencial pero menos sensible al parámetro.
- Hiperbólico tangente.

## Ventajas y desventajas
Las ventajas son:
- Entrenamiento sencillo.
- Sin óptimos locales.
- Buen escalado para espacios de datos altos.
- Sobreentrenamiento controlable.

Las desventajas son:
- Necesidad de una función kernel adecuada para la topología de los datos.
- Ajuste de parámetros laborioso.

# Árboles de decisión
Representación del proceso de decisión basándose en condiciones, para la representación de decisiones vinarias se usa la disyunción de conjunciones, la unión de los caminos que llevan a un resultado correcto.
## Generación de árboles
Dado un conjunto de ejemplos clasificados, se genera el árbol de decisión óptimo.
### ID3
El proceso de creación de árbol con ID3 se basa en el concepto de entropía, se seleccionan las distintas características y se calcula las entropías producidas al separarlas, el cálculo de la entropía es la suma ponderada de las varianzas de las clases creadas.

$I=-\sum\limits_{c}(n_{c}/n)\log_{2}(n_{c}/n)$
$I(A_I)=\sum(n_{ij}/n)I_{ij}$
$I_{ij}=-\sum\limits_{c}(n_{ijc}/n_{ij})\log_{2}(n_{ijc}/n_{ij})$
$G(A_{i})=I-I(A_{i})$
- C, conjunto de clases.
- n, número de patrones.
- $n_i$, número de patrones de la clase $i\in C$

La decisión de las características por nodo se basa en la minimización de la entropía.
### C4.5
Algoritmo basado en el ID3 con las siguientes modificaciones:
- Trabaja con valores continuos.
- Elección con ratio de ganancia.
- Post-poda de reglas.
- Costes de atributos.

### CART
Algoritmo basado en nodos que busca maximizar la pureza del sistema. Usando como medida de pureza el índice de Gini, proporcionando la probabilidad de un etiquetado erróneo de acuerdo a la distribución de clases. Este proceso se basa en la construcción de árboles donde las hojas contienen las impurezas, siendo la manera de controlar el ajuste se hace uso de la profundidad y anchura máximo del sistema.
## Usos de árboles
Los problemas adecuados para los árboles de decisión son aquellos donde los valores sean categóricos y difíciles de codificar, siendo robusta ante errores en datos y datos perdidos. Esto lleva a múltiples ventajas:
- Facilidad de interpretación, es fácil interpretar el proceso de decisión.
- Puede funcionar sin todos los datos.
- Funcionamiento con entradas categóricas.
- Permite múltiples valores de coste.

# Aprendizaje basado en instancias
Clasificación de nueva instancias basándose en similitud con instancias ya clasificadas. Esto se realiza acumulando el conjunto de entrenamiento con el que se comparara el nuevo valor.
Para ello hacemos uso de algoritmo **K-NN** que clasifica un nuevo caso en la categoría más frecuente de sus similares. 
Para el cálculo de las similitudes usamos la distancia euclídea, siendo muy importante la normalización previa al cálculo de la distancia.

$d(x_{i}, x_{j})=\sqrt{\sum\limits_{r=i}^{n}(x_{i}[r]-x_{j}[r])^{2}}$

Otras funciones de distancia serían:
- Manhattan.
- Minkowski.
- Coseno.
- Hamming.
- Correlación.

En este algoritmo el valor k será nuestro número de vecinos usados para el cálculo de la distancia, siendo los k más cercanos. Este valor regula la sensibilidad al ruido del sistema, pudiendo llevar a error en muy bajas y en muy altas al descarte de peculiaridades en la frontera de clases. Para evitar empate en el número de clases se hace uso siempre de K impares, otra opción es el uso de radio para la elección de vecinos, lo cual proporciona ventajas en sistemas con clases desbalanceadas.
### K-NN con rechazo
Se establecen criterios para dar garantías de la pertenencia a la clase, pudiendo rechazar elementos clasificados pero sin garantías de la veracidad de la clasificación.
### K-NN con distancia media
Se hace uso de la distancia de los casos para determinar la clase elegida, tomando la clase con la menor distancia media al dato a clasificar.
### K-NN con ponderación de vecinos
Se pondera los vecinos con su distancia al dato y peso del valor.

$\Large f'(x)=\frac{\sum\limits^{k}_{i=1}w_{i}f(x_{i})}{\sum\limits^{k}_{i=1}w_{i}}$

### K-NN con distancia mínima
Se reducen las clases a casos únicos posicionados en el baricentro o centroide de la clase, clasificando nuevos casos como la clase más cercana. Las ventajas de esta metodología es extremadamente eficiente pero con precisión dependiente de la dispersión de los datos de las clases.
### K-NN con ponderación de variables
Para el cálculo de la distancia se emplean pesos para establecer la importancia de cada variable en el establecimiento de la similitud entre casos.
# Evaluación
Para la evaluación de modelos se debe de diferenciar los deterministas donde una ejecución es suficiente para su evaluación y no determinista donde se deberá hacer la media de múltiples ejecuciones.
La evaluación se realiza sobre el conjunto de test, el cual debe ser representativo y seleccionado con uno de los siguientes métodos:
- Hold Out, se seleccionan datos aleatorios para el conjunto de test, es considerada una selección pesimista.
- Submuestreo aleatorio, se repite hold out multiples veces para no ser dependiente de un único experimento.
- Bootstrapping, se toma un número de datos del conjunto total, pudiendo repetir dato y se usan los no tomados para el test.
- Leave k-Out, separar k datos y entrenar con el resto, realizando esto un número de veces, sin repetir los datos k.
- Validación cruzada, se realizan experimentos usando como test todos los subconjuntos disjuntos, siendo k el número de subconjuntos sobre el conjunto total de orden aleatorio.

Para evaluar modelos se hace uso de múltiples test:
- Test de selección de modelos.
	- T-test, evaluación de los errores medios de los modelos, suponiendo que ambas distribuciones siguen una distribución normal con idéntica varianza.
	- Wilcoxon, evaluación de las diferencias de las medias de los modelos sin establecer ninguna suposición.
- Test de comparación múltiple
	- ANOVA, test paramétrico de comparación media.
	- Kruskal-Wallis, test no paramétrico de comparación de medias.

# Metaclasidicadores
Los diferentes clasificadores se pueden unir para crear sistemas con mayor precisión y fiabilidad, los métodos son los siguientes:
- Básicos.
	- Fusión de etiquetas.
		- Voto por mayoría, se asigna la clase con más votos.2
		- Mayoría absoluta, la clase debe conseguir la mitad de los votos más uno.
		- Voto por mayoría con umbral, mínimo de votos.
		- Voto por mayoría con peso, se ponderan los votos.
	- Fusión de salidas continuas, se asigna cada valor a una o varias clases.
	- Stacking, múltiples capas de clasificadores que terminan con una decisión categórica.
	- Cascada, uso de diferentes modelos para descartar progresivamente clases, funcionando los modelos en paralelo.
- Avanzados.
	- Bagging, se dividen los patrones en diferentes conjuntos de bootstrap para la utilización en diferentes clasificadores, seleccionando la salida más común como la correcta.
	- Aleatorización.
	- Boosting.
- Más comunes.
	- Random forest, se genera un conjunto de árboles mediante bagging y se selecciona un subconjunto aleatorio.
	- XGBoost, similar a random forest, pero mediante el uso de gradiente boosting, haciendo uso del descenso del gradiante sobre una función objetivo.