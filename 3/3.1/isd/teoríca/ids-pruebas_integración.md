Pruebas de componentes en conjunto para confirmar su correcto funcionamiento conjunto.
# Uso de DAOs
La prueva de componentes de manera unitaria puede necesidad del uso de un DAO, que se podrá sustituir por un falso normalmente. En los caso en los que no se pueda o se necesite hacer uso de la BD se crearan los datos y eliminaran los datos, para la creación y eliminación de información a causa de los tests se realizaran mediante los DAOs existentes, en caso de no haberlos se crearían.
# Maven
- /src
	- mein
		- java
		- resourds
	- test
		- java
		- resourds
- target
# Uso de BD
Las bases de datos usadas en las pruebas deben de ser una independiente de la usada en el funcionamiento normal del servicio.
