# Dibujo de líneas
Para el dibujado de líneas en pantalla tenemos dos opciones:
- Calculo directo, creación de la línea entre dos puntos con la aproximación a la matriz de píxeles para el pintado, tiene problemas por el uso de punto flotante y redondeos.
- Punto medio, cálculo basado en el uso único de sumas para el dibujo de líneas.
# Aliasing
Efecto de borde de sierra ocasionado por el dibujado de línea en posiciones diagonales, para la reducción de este efecto existen múltiples técnicas de anti-aliasing:
- Difuminado, proceso en el cual se reparte el valor de color de los píxeles de la línea no exactos entre las diferentes aproximaciones de manera proporcional.
- Supermuestreado, aumenta la densidad de píxeles para el cálculo de la línea y aplica a los píxeles reales una intensidad dependiente de la de sus sub píxeles correspondientes.
- Filtrado, uso de un filtro para realizar un difuminado general el típico es un kernel de paso bajo.
- Muestreo de área, se pintan los píxeles que coinciden con la línea de manera ponderada al área de la línea que ocupan.
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