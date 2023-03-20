# La neurona artificial
Las neuronas artificiales suman las entradas multiplicadas por su peso y el **bias** con su peso, el valor de salida se pasa por el **neta** a la función de salida. 
$$Y_{i}=f(\sum_{j=1}^{m} w_{ij}x_{j}+b_{i})$$

![[Pasted image 20230320084934.png]]
Las conexiones las podemos clasificar en función de su peso como:
- excitadoras $w_{ij}>0$
- inhibitorias $w_{ij}<0$
- inexistentes $w_{ij}=0$
Por otro lado, él bisas determina la sensibilidad de una neurona para la activación.
# Adaline
El modelo Adaline es un modelo supervisado con corrección de errores, corrige mediante la reducción del error cuadrático medio (ECM).
## Regala delta (LMS)
La regla delta o también conocida como el descenso del gradiente, basando se en la derivación del error y minimización de la pendiente de la derivada.
Para cada patrón k:
$Y_{k}=\sum_{j=0}^{m}w_{kj}x_{j}\\E$

## Descenso del gradiente
Se basa en la selección aleatoria de un valor para obtener la ecuación del error del gradiente, esta función se derivara para obtener la pendiente y, por lo tanto, se modificaran los pesos en función a la pendiente, llevando al mínimo error.
Dependiendo de la configuración del método de cálculo variará la resistencia a los errores de mínimo relativo. 
$$x_{n+1}=x_{n}-a\nabla f(x_{n})$$
# Perceptrón
Es el adaline, pero implementando una función de trasferencia para normalizar la salida.
Un perceptrón implementa un sistema de separación de conjuntos lineal.
## Regla de modificación de pesos
Algoritmo original:
1. Si está bien no lo toques.
2. Si la salida es incorrecta negativa, le sumo la entrada.
3. Si la salida es incorrecta positiva, le resto la entrada.
Luego se pasó a usar la regla delta:
$$w_{i}(t+1)=w_{i}(t)+\mu(d(t)-y(t))x_{i}$$
## Estructura y aprendizaje
## Funciones de transferencia
## Entrenamiento y 
# Aplicaciones
# Tags
#2- 
#2-2 
#si