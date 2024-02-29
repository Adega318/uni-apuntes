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
| Real N | VN           | FP             |
| Real P | FN             | VP             |

- $VPP=\frac{VP}{VP+VF}$
- $VPN=\frac{VN}{VN+FN}$
- $\Large F_{1}=(\frac{recall^{-1}+ precision^{-1}}{2})^{-1}$

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
$odds=\frac{p}{1-p}$
Donde el resultado está entre 0 e 1 indicando la relación entre la probabilidad de acierto y fallo.
Para hacer uso del odds, tomamos su logaritmo que lo llamamos logit:
$logit(p)=\log(\frac{p}{1-p})=z$
Despejamos la probabilidad del logit:
$e^{z}= \frac{p}{1-p} \to p=\frac{1}{1+e^{-z}}$

En estas operaciones z es representado como un modelo lineal, lo que nos permite interpretarlo y facilita la regularización.

# Máquinas de vectores de soporte
# Árboles de decisión
# Aprendizaje basado en instancias
# Evaluación
# Metaclasidicadores
# Redes de neuronas artificiales
# Aprendizaje bayesiano