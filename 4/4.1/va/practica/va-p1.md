# Histogramas
## ajustIntensity
Transformación de la imagen de un rango a otro.
- Numpy, para las matrices
	- mascaras, \[\], buenas para los planos.
Operaciones de punto a punto son representables como una operación lineal, en la cual el cambio en la pendiente cambia el contraste y desplazamiento el brillo.

$(M_{o}-m_{o})\frac{I-m_{i}}{M_{i}-m_{i}}+m_{o}$
## equalizeIntensity
Para realizar la ecualización se hace uso del histograma acumulado.

Se crea el histograma con el número de bins, sobre ese histograma se aplica la acumulación, se toma el punto central de cada bin y se interpola.
# Filtrado
## filterImage
I\[1:20, 1:20\] = fragmento de la imagen de 20x20

Para los zeros de tamaño hacemos uso de padding de la imagen.
## gaussKernel1D

## gaussFilter
$I*g_{1D}*g_{1D}^T$
## medianFilter
Dar el valor de la mediana del kernel
# Operadores morfológicos


# Detección de bordes
## edgeCanny
1. Gaussiana para sigma conocido.
2. Aplicar el gradiente.
3. Supresión no máxima.
	1. Interpolar cada pixel con su vector gradiente unitario positivo y negativo
	2. probar con un círculo para obtener bordes unitarios
4. Umbralización con histéresis
	1. Establecimiento de máximo y mínimo con tendencia a mantenerse en el anterior en caso de indeterminado.
	2. label scikit image