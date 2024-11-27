# Elementos deformantes
Basado en estados y las deformaciones como acciones para la minimización de la energía del sistema. Esta función de energía se puede basar en:
- Fuerzas internas, toma la forma del elemento deformante para calcular la energía del sistema.
	- Primera derivada, se realiza mediante la distancia de los nodos con sus vecinos, la reducción de este valor lleva a la contracción del contorno.
	- Segunda derivada, este valor al reducirse se obtiene formas con menor energía.
- Fuerzas externas, toma propiedades de la imagen como bordes o intensidades para el cálculo de la energía.
	- Bordes, se puede considerar la fuerza del borde en el cálculo de la energía para parar el movimiento al llegar a bordes, por otra parte, se hace uso de la distancia a borde para dirigir la contracción.