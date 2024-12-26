# Determinación de superficie visible
Hay dos principales opciones para la determinación de las superficies visibles:
- Para cada píxel determina los n objetos visibles para él.
- Para cada objeto determina las partes visibles.

Para realizar esto se puede hacer uso de diferentes tecnicas:
- Extensiones y volumenens de 
# Algoritmos


# Determinación de superficie visible
## Algoritmos
### Subdivisión de áreas
#### Warnock
Se subdivide el espacio, cuando en una de las subdivisiones aparecen múltiples objetos se repite el algoritmo. Con esto se establece el color a pintar en cada espacio y objetos a presentar.
#### Weiler-Atherton
Se ordenan los polígonos por profundidad y tomando el superior se recortan los inferiores y eliminan dichos recortes, esto se repetirá sucesivamente (siempre se corta con las originales, no las recortadas).
### Octrees
División recursiva del espacio tridimensional, obteniendo una representación la cual permite el fácil cambio de cámara.
### Trazado de rayos
Le lanza un "rayo" desde la cámara a cada uno de los píxeles de la imagen y tomamos el color del primer objeto encontrado.
