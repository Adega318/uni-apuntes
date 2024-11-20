# Determinación de superficie visible
## Algoritmos
### Subdivisión de áreas
#### Warnock
Se subdivide el espacio, cuando en una de las subdivisiones aparecen múltiples objetos se repite el algoritmo. Con esto se establece el color a pintar en cada espacio y objetos a presentar.
#### Weiler-Atherton
Se ordenan los polígonos por profundidad y tomando el superior se recortan los inferiores y eliminan dichos recortes.