# Opciones de desarrollo
Dentro de las opciones de desarrollo podemos crear sitios independientes para sobremesa y móvil, siendo el método usado en el pasado, hoy en día se usa un diseño adaptable. Este método es soportado por los navegadores móviles mediante HTML5 y CSS3.
## HTML 5
En HTML el concepto principal a tener en cuenta es el **Viewport**, siendo dependiente del dispositivo. En móvil este viewport es escalado al tamaño del móvil, lo que puede llevar a tamaños inadecuados, lo que se puede mitigar con tags para establecer atributos como no escalables.
## CSS 3
En css la principal herramienta son la **media queries** que permiten especificar css dependiente del dispositivo usado, Media tiene los siguientes parámetros:
- type
- max-device-width / min
- max-width / min
- orientation
- aspect-ratio
- max-device-pixel-ratio / min
- resolution
# Interacción con dispositivos móvil
La interacción con dispositivos móviles es necesario tener en cuenta el uso de pantallas táctil.
## Eventos
Los eventos en una pantalla táctil cambian, desapareciendo el mouse over o mouse move y apaceriendo el tap.
## Formularios
Los formularios deben ser adaptados al móvil, cambiando los tipos text planos a tipos más concretos para la información requerida y evitando la obstrucción de elementos por el formulario.
# Conectividad
La conectividad en móvil se ve sometida a las redes móviles, haciendo necesaria la optimización del código, algunos métodos son:
- Minimización de tamaño.
	- Eliminar espacios.
	- No cargar recursos no usados.
	- Compresión de imágenes.
	- Empleo de versiones mínimas de librerías.
- Peticiones AJAX (lazy loading).
# Rendimiento
El redimiendo debe ser optimizado par móvil, con métodos como:
- Empleo de código simple.
- Reducir las peticiones HTTP.
- Evitar el empleo de CSS de alto consumo.
- Empleo de CSS sprites para imágenes pequeñas.
# Geolocalización
Los dispositivos móviles tienen la capacidad de proporcionar información asíncrona de posición. Necesitando normalmente de permisos y con la capacidad de establecer la calidad y frecuencias de actualización de posición.
# Herramientas de desarrollo y pruebas