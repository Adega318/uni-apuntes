# Dibujo de líneas
Para el dibujado de líneas en pantalla tenemos dos opciones:
- Calculo directo, creación de la línea entre dos puntos con la aproximación a la matriz de píxeles para el pintado, tiene problemas por el uso de punto flotante y redondeos.
- Punto medio, cálculo basado en el uso único de sumas para el dibujo de líneas.
# Aliasing
Efecto de borde de sierra ocasionado por el dibujado de línea en posiciones diagonales, para la redución de este efecto existen multiples tecnicas de anti-aliasing:
- 
# Relleno de polígonos
## Métodos de inundación
El procedimiento de inundación es usado cunado no hay definición de los objetos, siguiendo los siguientes pasos:
- Inicio
- Modificación
- Propagación, escoger píxeles cercanos a ser modificados para lo cual se debe establecer un criterio.
- Final
## Inundación recursiva
Método basado en el lanzamiento recursivo de la inundación con propagación de 4-8 vecinos por ciclo.
## Inundación por barrido
Método donde sobre un pixel semilla se propaga sobre una línea de barrido, revisando huecos inferiores y superiores, los cuales serán los puntos semilla de consecuentes inundaciones.
## Soft-filling