- Names, identificadores y símbolos.
- Bindings, asociación de un nombre y un término.
- Scope, extensión del programa durante la cual un Binding concreto es activo.

# Binding
La carateristica más importante de un binding es su Binding Time, punto de procesado de un programa donde un binding es creado o una decisión de implementación es tomada. Esto es importante, ya que tiempos bajos se son altamente eficientes y tiempos altos altamente flexibles, en lenguajes compilados suelen encontrarse tiempos bajos. Los bindings se pueden realizar en los siguientes momentos:
- Escritura de programa
- Compilación
- Linking
- Carga
- Ejecución

## Tiempo de vida y manejo de almacenamiento
Dentro denuesto programa tenemos los siguientes eventos destacados:
- Creación
	- Objetos
	- Bindings
- Referencias a variables
- Desactivación y reactivación de bindings
- Eliminado
	- Objetos
	- Bindings

El tiempo entre la creación y eliminación de un binding es llamado ***Lifetime*** y a la zona del programa contenida en este lifetime es conocida como scope.

El almacenamiento se divide en los siguientes metodos:
- Estatica
	- Codigo
	- Globales
	- Variables estaticas
	- Constantes
- Pila, 
	- Parametros
	- Variables locales
	- Temporales
- Heap
	- 