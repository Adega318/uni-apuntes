Operaciones de bajo nivel con el objetivo de convertir una imagen en una versión de la misma más digerible para otros sistemas. Estos métodos se basan en las propiedades de la consistencia y redundancia de las imágenes para capturar los grandes cambios en las mismas, lo que se suele corresponder con bordes u otros detalles.
# Tipos de preprocesado
- Transformaciones puntuales en el Nivel de gris, se modifica uno de los niveles de gris de todos los píxeles a otro nivel.
	- Corrección de nivel de gris, elimina errores en la imagen mediante la recuperación del nivel original de gris.
	- Modificación de la escala de grises, aplicado de una función para la modificación del histograma. 
		- **Rango dinámico**, expansión de la información para que ocupe todo el rango. $\LARGE g_{norm}(x,y)= G_{minNorm}+\frac{(G_{maxNorm}-G_{minNorm})\times (g(x,y)-G_{min})}{G_{max}-G_{min}}$
		- **Ecualización**, operación para aplanar un histograma para dar la misma importancia a todos los píxeles, expandiendo el rango de píxeles con mayor concentración y concentrando las partes de menor densidad. Para esto se crea una función monótona acotada acorde a la imagen, siendo el histograma acumulado donde la cota es el número de píxeles de la imagen y monótona creciente, esta función se basa en el crecimiento por la acumulación de píxeles, por lo tanto, cuando hay valores similares son almacenados sobre el mismo y cuando hay alto diferencial se aplica a diferentes valores.
		- **Control adaptativo**, aplicación a bloques del histograma ecualizaciones, causando bordes entre bloques, lo cual se soluciona mediante técnicas de corrección. $\LARGE g_{adapt}=K_{1}*|\frac{\mu_{local}}{\sigma_{local}}|(g(x,y)-\mu_{global})+K_{2}\mu_{global}$
- Transformaciones geométricas, modificación de la relación espacial entre píxeles.
	- Transformaciones
		- **Traslación**, movimiento lineal de los píxeles, definido por un vector. $P'=P+T$
		- **Rotación**, movimiento de los píxeles con respecto a un punto de giro. $P'=P\times R$
		- **Escalado con respecto al origen**, la posición del punto es multiplicada por un valor. $P'=P\times S$
	- Coordenadas homogéneas, para realizar múltiples transformaciones con un único paso se hace uso de una coordenada extra. Esta coordenada extra hace que todas las operaciones sean multiplicaciones, lo que permite pre multiplicar las matrices para obtener la matriz de transformación combinada.
- Métodos de vecindad local
- Operaciones Morfológicas

# Interpolaciones
Procesos usados para la elección de los niveles de gris de los píxeles en función de los píxeles ya conocidos.