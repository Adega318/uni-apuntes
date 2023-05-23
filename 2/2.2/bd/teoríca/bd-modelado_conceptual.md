# Entidad
Una entidad es algo en el mundo real, distinguible del resto de algos, cada entidad tiene propiedades definidas como atributos. Cada entidad tiene un valor para cada atributo.
## Tipos
Se pueden agrupar las entidades similares en grupos, los tipos de entidad los podemos definir basándose en las entidades con atributos iguales.
### Atributos
Los atributos se pueden separar en:
- Simples y atómicos, atributos no divisibles.
- Compuestos, son divisibles en componentes menores.
- Monovaluados, atributos con solo un valor
- Multivaluados, atributos con valores dependiente de una condición o dato externo.
- Almacenados y derivados, los almacenados son guardados en la BD y los derivados calculados con los anteriores.
# Relaciones
Una relación es la interacción entre dos entidades. En las relaciones no se pueden dar repeticiones ni vacíos.
Se representan por un rombo conectado a las entidades.
## Recursivas
Son relaciones donde en los dos extremos son el mismo tipo de entidad.
Se representa con una de ida y una de vuelta.
## Cardinalidad
La cardinalidad es la indicación de los números en la relación.
- 1:1, uno a uno.
- 1:N, uno a muchos.
- N:M, muchos a muchos.
Se representa por los números en los lados.
## Participación
La participación de las entidades puede ser parcial o total, dependiendo si todos son involucrados.
Se representa como línea doble en el lado total y simple en el parcial.
# Tipos entidad débil
Entidades sin los suficientes atributos para formar un identificador. Esto hace que se deba establecer una dependencia de una entidad más fuerte. Las cardinalidades N:M no pueden tener entidad débil, siempre serán 1:N con la baja en la N también tendrá dependencia de existencia (doble ralla).

![[Pasted image 20230315114323.png]]

$DI\rightarrow DE$
$DE!\rightarrow DI$
# Trampas de conexión
Problemas causados por el orden de las conexiones, hay dos tipos:
## Abanico
Producido por caminos ambiguos entre relaciones o teniendo más de dos tipos de relación con cantidad N.

![[Pasted image 20230315120128.png]]
![[Pasted image 20230315114854.png]]

Solución:

![[Pasted image 20230315120334.png]]

## Sumidero
Se produce al no haber camino entre entidades relacionadas. Aparece cuando uno o más tipos de relaciones tienen participación parcial.

![[Pasted image 20230315120111.png]]
![[Pasted image 20230315120046.png]]

Solución:

![[Pasted image 20230315120309.png]]

# Relaciones de grado mayor a 2
Relación ternaria de N:N:N.

![[Pasted image 20230322120314.png]]

## Diferencia entre ternaria y múltiples binarias
En las múltiples binarias no se representa la conexión todos con todos producida por la ternaria, perdiendo información. Esta perdida de datos se puede reparar con el enriquecimiento del modelo.
# Modelización temporal
Tenemos tres principales alternativas en  la representación de temporalidad que pueden ser combinadas:
## Histórico por atributo
Para almacenar la temporalidad de atributos asíncronos, creamos varias lineas temporales para los varios atributos (registrar el historial de salarios y proyectos).

![[Pasted image 20230329135956.png]]

## Histórico único
Uso de una única linea temporal para el almacenamiento de atributos asíncronos, almacenando una nueva entrada para el cambio de cualquiera.

![[Pasted image 20230329140744.png]]

## Imagen especular
La imagen especular basase en el almacenamiento de la información actual y por separado las imágenes históricas de la información.

![[Pasted image 20230329142047.png]]

# Tags
#2- 
#2-2 
#bd