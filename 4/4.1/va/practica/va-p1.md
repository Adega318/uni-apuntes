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

## filterImage
I\[1:20, 1:20\] = fragmento de la imagen de 20x20

Para los zeros de tamaño hacemos uso de padding de la imagen.