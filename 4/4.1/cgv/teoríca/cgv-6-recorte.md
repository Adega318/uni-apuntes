El recorte es el método de cálculo único para los objetos dentro del área de vista.
# Recorte 2D
## Puntos
Para el recorte de puntos se comprueban la pertenencia de las coordenadas al espacio de recorte.
## Línea
El recorte de líneas se basa en comprobar la posición de los puntos con respecto al área de vista:
- Ambos dentro, pintar.
- Uno dentro, cálculo de la intersección y pintado.
- Ambos fuera, cálculo de la posible intersección y pintado en caso de necesario.

Para el cálculo de intersecciones se prolongan las líneas, 
# Recorte 3D