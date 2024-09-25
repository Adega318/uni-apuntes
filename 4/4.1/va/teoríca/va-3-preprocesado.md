Operaciones de bajo nivel con el objetivo de convertir una imagen en una versión de la misma más digerible para otros sistemas. Estos métodos se basan en las propiedades de la consistencia y redundancia de las imágenes para capturar los grandes cambios en las mismas, lo que se suele corresponder con bordes u otros detalles.
# Tipos de preprocesado
- Transformaciones puntuales en el Nivel de gris, se modifica uno de los niveles de gris de todos los píxeles a otro nivel.
	- Corrección de nivel de gris, elimina errores en la imagen mediante la recuperación del nivel original de gris.
	- Modificación de la escala de grises, aplicado de una función para la modificación del histograma.
- Transformaciones geométricas
- Métodos de vecindad local
- Operaciones Morfológicas

50-150

50 -> 0
150 -> 255

$\large|x-50|*\frac{255}{100}$
