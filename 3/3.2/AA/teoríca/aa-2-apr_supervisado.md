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

# Regresión logística
# Máquinas de vectores de soporte
# Árboles de decisión
# Aprendizaje basado en instancias
# Evaluación
# Metaclasidicadores
# Redes de neuronas artificiales
# Aprendizaje bayesiano