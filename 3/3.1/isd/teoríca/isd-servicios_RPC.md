# Modelo RPC
El remote procedure call se basa en:
- Un proceso expone sus funcionalidades como una serie de procedimientos ejecutables desde cualquier punto de la red.
- Facilidad de invocar operaciones remotas con la facilidad de una local.
- Abstracción de la creación, envió y recepción de mensajes por red.
El rcp requiere los siguientes pasos para la implementación:
- aplicación servidora:
	- Modelación de la operación ofrecida.
	- Definición de las operaciones en un fichero de definición.
	- Generación de un skeleton con el fichero de definición.
	- Implementación de las funciones sobre el skeleton
- aplicación cliente:
	- Ejecutar compilación para generar la definición.
	- Invocar las operaciones del servidor.
# Thrift
# REST vs RPC