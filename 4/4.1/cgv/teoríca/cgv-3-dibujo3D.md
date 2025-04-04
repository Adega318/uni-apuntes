# Proyecciones
## Tipos
- Perspectiva, proyección con un número de puntos de fuga, por lo que todas las líneas paralelas se terminan uniendo en ellos.
- Paralelas
	- Ortogonal, el plano de proyección es perpendicular al objeto.
		- Planta alzado y perfil
		- Axonométrica
			- Isométrica
	- Oblicua, el plano de proyección no es perpendicular al objeto.
		- Caballera
		- Gabinete

## Elementos de definición
Elementos a definir a la hora de crear una proyección.
- VRP, punto de la cámara en el sistema de coordenadas.
- VPN, vector de apuntado de la cámara.
- VUP, vector indicando la dirección "arriba" en la cámara.
- Tipo de proyección.
- Volumen de vista, espacio a renderizar en la proyección.

# Generación de vistas 3D
Para la generación de vistas se hace uso de coordenadas homogéneas, las cuales añaden una nueva coordenada "W", siendo una optimización para permitir el trabajo con matrices de tamaño constante.
Para la generación de perspectivas se toma el punto de la cámara, plano de proyección y vértices del objeto y mediante aristas entre la cámara y vértices y su consecuente proyección en el plano se obtiene la perspectiva, si la cámara se lleva al infinito esta perspectiva se convierte en paralela.
Para las proyecciones se debe definir un centro de proyección (COP), el cual es descrito por dos valores, sus coordenadas y su vector de apuntado.