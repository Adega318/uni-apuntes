# Histogramas
## ajustIntensity
Transformación de la imagen de un rango a otro.
- Numpy, para las matrices
	- mascaras, \[\], buenas para los planos.
Operaciones de punto a punto son representables como una operación lineal, en la cual el cambio en la pendiente cambia el contraste y desplazamiento el brillo.

$(M_{o}-m_{o})\frac{I-m_{i}}{M_{i}-m_{i}}+m_{o}$

## equalizeIntensity
Para realizar la ecualización se hace uso del histograma acumulado.