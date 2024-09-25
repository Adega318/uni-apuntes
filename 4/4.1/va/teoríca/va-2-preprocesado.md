Operaciones de bajo nivel con el objetivo de convertir una imagen en una versión de la misma más digerible para otros sistemas. Estos métodos se basan en las propiedades de la consistencia y redundancia de las imágenes para capturar los grandes cambios en las mismas, lo que se suele corresponder con bordes u otros detalles.
# Tipos de preprocesado
- Transformaciones puntuales en el Nivel de gris, se modifica uno de los niveles de gris de todos los píxeles a otro nivel.
	- Corrección de nivel de gris, elimina errores en la imagen mediante la recuperación del nivel original de gris.
	- Modificación de la escala de grises, aplicado de una función para la modificación del histograma. 
		- Rango dinámico, expansión de la información para que ocupe todo el rango.$\LARGE g_{norm}(x,y)= G_{minNorm}+\frac{(G_{maxNorm}-G_{minNorm})\times (g(x,y)-G_{min})}{G_{max}-G_{min}}$
		- Ecualización, operación para aplanar un histograma para dar la misma importancia a todos los píxeles, expandiendo el rango de píxeles con mayor concentración y concentrando las partes de menor densidad. Para esto se crea una función monótona acotada acorde a la imagen, siendo el histograma acumulado donde la cota es el número de píxeles de la imagen y monótona creciente.
- Transformaciones geométricas
- Métodos de vecindad local
- Operaciones Morfológicas
