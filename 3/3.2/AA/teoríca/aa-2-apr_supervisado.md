# Introducción
En el aprendizaje buscamos que el sistema generalice el conocimiento para permitir su funcionamiento sobre nuevos datos.
Para lo siguiente debemos distinguir entre parámetros e hiperparámetros:
- Parámetros, valores que definen el comportamiento del modelo.
- Hiperparámetros, parámetros definidos para el control del proceso de aprendizaje.

Por otra parte, se debe de controlar el sobre ajuste e infra ajuste; para ello se debe controlar la complejidad del modelo, tratando de llegar a una buena generalización, evitando el ajuste excesivo a los datos de entrenamiento. Otros aspectos ajustables son el número de ejemplos disponibles y error de generalización.
## Vapnik-Chervonenkis
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
Proceso de mejorar la calidad de los datos del dataset para potenciar las características interesantes para el entrañamiento del sistema.
### Transformaciones
#### Limpieza de datos
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
	- Min/max, sé plasman los valores en un rango, $\Large v'=\frac{v-min}{max-min}(nuevomax-nuevomin)+nuevomin$
	- Escalado decimal, sé mueve el punto decimal en los valores del atributo $\Large v'=\frac{v}{10^{j}}$
	- Media cero, normalización para datos con algún dato fuera de lo normal $\Large v'=\frac{v-\mu}{\sigma}$
- Agregación, unión de atributos basándonos en el conocimiento del problema.
- Generalización, sustitución de datos precisos por datos más abstractos y sencillos.

#### Reducción de datos
- Análisis de componentes principales (PCA)
- Análisis de componentes independientes (ICA), técnica para obtener las fuentes originales sin datos extra.

## Evaluación de sistemas
### Clasificadores
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
- Curva ROC, curva donde la x es la tasa de falsos positivos e y la de verdaderos positivos; esta curva se puede modificar usando el umbral en la salida.
- Índice Kappa, cálculo de la probabilidad, aciertos aleatorios.

| A\B      | Negativo | Positivo |
| -------- | -------- | -------- |
| Negativo | a        | b        |
| Positivo | c        | d        |

$\Large P_{e}= \frac{(a+b)\times(a+c)+(c+d)\times(b+d)}{n^{2}}$
$\Large P_{0}= \frac{a+d}{n}$
$\Large K=\frac{P_{0}-P_{e}}{1-P_{e}}$


# Regresión logística
Técnica de clasificación basada en el uso de regresiones lineales.
Para esto usamos el odds, siendo:

$\Large odds=\frac{p}{1-p}$

Donde el resultado está entre 0 y 1 indicando la relación entre la probabilidad de acierto y fallo.
Para hacer uso del odds, tomamos su logaritmo que lo llamamos logit:

$\Large logit(p)=\log(\frac{p}{1-p})=z$

Despejamos la probabilidad del logit:

$\Large e^{z}= \frac{p}{1-p} \to p=\frac{1}{1+e^{-z}}$

En estas operaciones z es representado como un modelo lineal, lo que nos permite interpretarlo y facilita la regularización.

$\Large p=\frac{1}{1+e^{-(b_{0}+\sum b_{i}x_{i})}}$

Gracias a la regresión mediante z reducimos los impactos de los valores atípicos, también beneficiando en la normalización dando valores entre 0 y 1.

## Entrenamiento
Para el entrenamiento se usan técnicas similares a las empleadas en los perceptrones.
Siendo la maximización para n observaciones:
$LL = \sum [y\times log(p)+(1-y)\times log(1-p)]$
Aplicándole una técnica de ascenso del gradiante, siendo la técnica de descenso del gradiante con el signo inverso.
## Regularización
Proceso de evitar el aumento excesivo de ciertos parámetros para evitar el sobre ajuste.
### Lasso (L1)
Técnica que agrega a la función de coste un término de penalización que es proporcional al valor absoluto de los coeficientes, reduce los valores llevándolos a 0, consiguiendo en algunos casos anular parámetros.
### Ridge (L2)
Similar a l1 pero usando los coeficientes al cuadrado, reduciendo los coeficientes sin llevarlos a 0, aumentando la estabilidad.
### Elastic Net
Modelo que usa en combinación L1 y L2, pudiendo implementar regulación de implicación de cada una.
### Tikhonov
Complicado.
### Norma Max
Establecimiento de un valor máximo para los parámetros.
### Dropout
Técnica de desactivación de parámetros cuando se vuelven demasiado importantes.
### Parada temprana
Técnica basada en parar el entrenamiento iterativo de manera temprana para evitar el sobre ajuste.
# Máquinas de vectores de soporte
Sistema de clasificación binaria (-1, 1) similar a un perceptron.
## Problemas linealmente separables
Para resolver problemas linealmente separables se define un hiperplano y sus positivos y negativos (márgenes), maximizando la distancia de los márgenes al hiperplano; siendo los datos sobre el margen los vectores de soporte.
## Problemas no linealmente separables
Para clasificar se debe de permitir cierta holgura y fallo. Permitimos fallos en la clasificación en la zona de margen del hiperplano, teniendo el parámetro C para elegir la prioridad de los márgenes sobre la holgura.
En caso de no querer considerar error se proyecta los datos en un hiperespacio para poder usar un hiperplano para separar los datos. Para construir este plano se hace uso del truco del kernel, donde se crea una función que transforma nuestros vectores en su proyección, permitiéndonos usar varios tipos de kernels para realizar esta función.
## Ventajas y desventajas
Las ventajas son:
- Entrenamiento sencillo.
- Sin optimos locales.
- Buen
# Árboles de decisión
# Aprendizaje basado en instancias
# Evaluación
# Metaclasidicadores
# Redes de neuronas artificiales
# Aprendizaje bayesiano