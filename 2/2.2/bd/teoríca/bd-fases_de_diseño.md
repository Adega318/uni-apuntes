# Fases del diseño
## Modelo conceptual
Diseño de la base de datos independiente de la implementación [SGBD](https://es.wikipedia.org/wiki/Sistema_de_gesti%C3%B3n_de_bases_de_datos), siendo un modelo altamente semántico.
## Diseño lógico
En función al modelo conceptual se crea un esquema lógico basándose en un modelo (IB: Modelo relacional). En esta fase se introduce el [SGBD](https://es.wikipedia.org/wiki/Sistema_de_gesti%C3%B3n_de_bases_de_datos).
## Diseño físico
El diseño físico es la implementación del esquema lógico atendiendo al [SGBD](https://es.wikipedia.org/wiki/Sistema_de_gesti%C3%B3n_de_bases_de_datos) y a la infraestructura y requerimientos presentados.
![[Pasted image 20230217203700.png]]
# Técnicas
## Ascendente
Técnica purista que implica contemplar el diseño de esquemas de bases de datos utilizando la semántica de los atributos, que es capturada por una serie de relaciones entre atributos (dependencias funcionales, dependencias multivaluadas y dependencias de join). Se basa en una técnica denominada [[bd-diseño_lógico#Normalización|Normalización]].
## Descendente
Técnica que se emplea actualmente en el diseño de aplicaciones de bases de datos comerciales. Diseñar un esquema conceptual (modelo ER) y luego transformar el esquema conceptual en un conjunto de relaciones utilizando el procedimiento de transformación E/R a MR.
# Tags
#2- 
#2-2 
#bd