Dentro del prototipado al diseño de la interfaz se le llama wireframe y se diferencian varios niveles de fidelidad con el producto final:
- Baja, características generales de la interfaz ( hecho a mano )
- Media,  prototipo mas preciso con los elementos perfectamente definidos.
- Alta, prototipo medio con el estilo establecido ( igual al producto final ).

# Implementar interfaces
La implementación de interfaces comienza con la elección de una librería adecuada, debe tener los correctos bindings para nuestro lenguaje y función en el sistema deseado (GTK librería nativa de gnome).
## Layout
La distribución de la interfaz se basa en la creación de contenedores.
- Window
	- Box
		- Label
		- Button

## Independencia de la interfaz
Se establece la interfaz y el fondo, en estas practicas lo principal es la sincronización entre ambas