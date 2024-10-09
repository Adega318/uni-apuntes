# Modelado de objetos
El modelado de objetos mediante la definición de polígonos no se hace uso para el diseño de objetos, pero sí para la representación de los mimos para su procesado por la tarjeta gráfica. El proceso de definición de polígonos se debe definir los vértices y la normal de los polígonos (lado de la cara hacia fuera).
## Formas
## Representaciones de barrido
Método de representación de objetos que cuentan de un eje de simetría, esta representación se realiza mediante el uso de un eje y sección. Habiendo dos tipos:
- Traslacional, movimiento de la sección sobre el eje.
- Revolución, giro de la sección (perfil) sobre el eje.
## División espacial
Se convierte un objeto en un conjunto de primitivas contiguas no intersecadas, normalmente usado para simulaciones de fuerzas físicas sobre el objeto.
## Geometría sólida constructiva
Se hace uso de la intersección y unión de objetos para la creación de uno nuevo, esto se consigue por la generación de un árbol de operaciones con las formas que componen el objeto.
# Fractales
Para la representación de formas orgánicas y naturales el acercamiento euclídeo es inapropiado, por ello se hace uso de los fractales. Esto nos permite la creación de modelos con niveles de detalle infinitos, ya que al hacer zoom se genera de manera recursiva el fractal. Estos fractales junto de otras técnicas se puede usar para la generación de topologías y otros elementos.
## Movimiento Browniano
En el proceso de generación de fractales se establece desplazamientos aleatorios para generar diferencias en la generación.
## Dibujo de curvas paramétricas
### Representación paramétricas
Para la representación paramétrica se hace uso de un segmento (Q) definido por un vector (T) y matriz de coeficientes (C) a su vez dependiendo del orden de la figura se necesitará un número de puntos de control igual al orden más uno.
### Continuidad
La continuidad es el proceso de unión de curvas sin interrupciones, siendo de dos tipos:
- Geométrica, igualdad de las direcciones de los vectores tangentes.
- Paramétrica, igualdad de direcciones y magnitudes de los vectores tangentes del los segmentos.
### Splines
Para definir las curabas con splines se hace uso de un matiz base y un conjunto de segmentos 
#### Uniforme no-racional
Spline definido por puntos de control y segmentos los cuales cada uno tiene relacionados tres puntos de control. Este acercamiento tiene el problema de no poder hacer pasar a la curva por un punto concreto.