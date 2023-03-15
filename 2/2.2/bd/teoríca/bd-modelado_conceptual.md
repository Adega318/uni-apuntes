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
**DI -> DE
DE !-> DI**
# Trampas de conexión
Problemas causados por las conexiones, divididas en dos tipos:
- Abanico, producido por caminos ambiguos entre relaciones o teneiendo mas de dos tipos de relación con cantidad N.
![[Pasted image 20230315114854.png]]
- Sumidero
# Tags
#2- 
#2-2 
#bd