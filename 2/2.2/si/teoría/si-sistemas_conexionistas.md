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
Al añadir múltiples perceptrones se pasó de hacer separaciones lineales a poder hacer separaciones polinómicas. Tambien produce el efecto de caja negra sobre el funcionamiento interno de la red.
![[Pasted image 20230320174935.png]]
Arquitectura multicapa:
- Capa de entrada, neuronas que retransmiten las entradas a las capas ocultas.
- Capas ocultas, procesan la información y mandan a las de salida.
- Capa de salida, reciben los datos de salida.
## Funciones de transferencia
### Escalón
![[Pasted image 20230322104454.png]]
### Lineal y lineal mixta
![[Pasted image 20230322104439.png]]
### Sigmoidal
$$f(n)=\frac{2}{1+e^{-2n}}-1$$
### Hiperbólica
## Entrenamiento y Aplicaciones
Las redes neuronales son aproximaciones universales, siendo garantizado su validez para cualquier problema asegurado por el teorema de la aproximación universal.
# Tags
#2- 
#2-2 
#si