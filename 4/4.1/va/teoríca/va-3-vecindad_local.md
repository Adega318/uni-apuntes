# Convolución 2D
La convolución se basa en el paso de un filtro por todos los píxeles de una imagen, este filtro es una matriz de MxN, donde el contenido de la misma determina el efecto (la suma de los elementos del filtro es 1).
Este proceso lleva a una imagen más pequeña a no ser que se añada un padding para compensar.
## Suavizado
## Detallado
## Acentuado de bordes
### Laplaze
### Algoritmos de realce
Para realzar la una imagen se calcula un realce y se le resta a la imagen original.
## Eliminación de ruido

# Operadores morfológicos
Operaciones basadas en la forma de los conjuntos de píxeles, estas operaciones se realizan mediante el cálculo de conjuntos y, por lo tanto, se consideran las imágenes conjuntos.
## Dilatación
## Erosión
## Apertura
Concatenación de erosión y dilatación con un mismo elemento estructurante, permitiendo la eliminación de ruido con posterior recuperación parcial de las formas no eliminadas. Esto lleva a un efecto de eliminación de ruido y suavizado de bordes.
## Cierre
Concatenación de dilatación y erosión con un mismo elemento estructurante, eliminando agujeros en figuras y conectando las adyacentes.