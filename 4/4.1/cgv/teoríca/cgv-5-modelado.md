# Modelado de objetos
## Superficie de polígonos
La representación de objetos se realiza mediante un conjunto de polígonos (triángulos) definidos por una serie de vértices.  Estos polígonos tienen una normal definida por el orden de declaración de los vértices, esta normal indica la dirección de la superficie del polígono.
## Formas
La definición de formas comunes:
- Esfera
- Elipsoide
- Toro

Son predefinidas y sujetas a específicas optimizaciones.
## Representación de barrido
Creación de un objeto basada en un eje mediante el uso de una sección la cual es usada como:
- Traslacional, movimiento de la sección sobre el eje para la definición de la superficie.
- Revolución, rotación de la sección en torno al eje para formar una superficie.

## División espacial
Representación de un objeto por un conjunto de primitivas contiguas no intersecadas, usada principalmente para simulación de fuerzas.
## Geometría sólida constructiva
Objetos creados por operaciones en forma de árbol entre primitivas.
# Fractales
Formas creadas por operaciones recursivas con nivel de detalle infinito y auto-similitud (estructuras recurrentes).
## Movimiento Browniano
En el proceso de generación de fractales se establece desplazamientos aleatorios para generar diferencias en la generación.
# Dibujo de curvas paramétricas
## Representación paramétricas
Para la representación paramétrica se hace uso de un segmento (Q) definido por un vector (T) y matriz de coeficientes (C) a su vez dependiendo del orden de la figura se necesitará un número de puntos de control igual al orden más uno.
## Continuidad
La continuidad es el proceso de unión de curvas sin interrupciones, siendo de dos tipos:
- Geométrica, igualdad de las direcciones de los vectores tangentes.
- Paramétrica, igualdad de direcciones y magnitudes de los vectores tangentes del los segmentos.

## Splines
Para definir las curabas con splines se hace uso de un matiz base y un conjunto de segmentos 
### Uniforme no-racional
Spline definido por puntos de control y segmentos los cuales cada uno tiene relacionados tres puntos de control. Este acercamiento tiene el problema de no poder hacer pasar a la curva por un punto concreto.
### No uniforme no-racional
Spline donde se hace uso de funciones de mezcla, las cuales permiten la estipulación de puntos obligatorios para la curva aunque disminuyendo la continuidad a C1.
## Subdivisión de curvas
Proceso por el cual se duplican los puntos de control mediante la búsqueda de puntos intermedios a los ya definidos.
## Superficies bicúbicas
# Otros métodos
## Ropa
## Pelo
## Vegetación
## Representación de terreno
