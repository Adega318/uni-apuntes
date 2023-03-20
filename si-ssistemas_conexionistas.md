# La neurona artificial
Las neuronas artificiales suman las entradas multiplicadas por su peso y el **bias** con su peso, el valor de salida se pasa por el **neta** a la función de salida.
<font size="6"> $$y=f(\sum_{i=1}^{n} w_{i}x_{i}+b)$$ </font>

![[Pasted image 20230320084934.png]]
## Punto de activación
Recta imaginaria que divide los niveles de activación de las neuronas en abierto y cerrado.
## Entrenamiento
El entrenamiento básico se basa en series de datos pre procesados.
# Adaline
Uno de los primeros modelos, siendo un modelo supervisado.
El método de corrección se basa en un algoritmo de optimización, descenso del gradiente. Esto se aplicará a un espacio de dimensiones igual a las variables.
## Descenso del gradiente
Se basa en la selección aleatoria de un valor para obtener la ecuación del error del gradiente, esta función se derivara para obtener la pendiente y, por lo tanto, se modificaran los pesos en función a la pendiente, llevando al mínimo error.
Dependiendo de la configuración del método de cálculo variará la resistencia a los errores de mínimo relativo.
<font size="6"> $$x_{n+1}=x_{n}-a\nabla f(x_{n})$$ </font>
# Perceptrón
## Estructura y aprendizaje
## Funciones de transferencia
## Entrenamiento y 
# Aplicaciones
# Tags
#2- 
#2-2 
#si