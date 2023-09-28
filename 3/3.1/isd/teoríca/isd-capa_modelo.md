# Principios de diseño
La capa modelo debe ofrecer una api que permita:
- invocar casos de uso
- oculte detalles de implmentacción
# Método de desarrollo
## Modelado de entidades
Las entidades en el contesto de isd son tablas, con sus campos correspondientes. 
## Definición de la API
1. Agrupación de los casos de uso.
	- las agrupaciones deben de ser lógicas.
2. Definición de interfaces para los grupos.
	- un método por caso de uso.
	- las interfaces aplican el método de diseño fachada.

