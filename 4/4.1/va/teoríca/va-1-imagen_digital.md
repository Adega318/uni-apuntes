# Conceptos básicos
Una imagen es una representación acotada del mundo, estas imágenes pueden ser representadas mediante señales y, por lo tanto, transformadas por funciones.
Estas señales pueden ser almacenadas como mapas de vectores, siendo la manera más precisa pero difícil de obtener o almacenadas como mapas de bits, mucho más sencillas. Estas imágenes de mapa de bits están compuestas por píxeles, los cuales tienen asociados unas coordenadas e información.
# Algoritmo de cálculo de componentes conexas
```
Paso1. Para cada pixel negro se analizan los vecinos superior e izquierdo.
	- Si ambos son blancos se asigna una nueva etiqueta.
	- Si uno es negro se le asigna al actual su etiqueta.
	- Si ambos son negros se unen las etiquetas de ambos.
Paso2. 
```