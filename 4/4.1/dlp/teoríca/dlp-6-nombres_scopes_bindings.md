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
Dentro de nuesto programa tenemos los siguientes eventos destacados:
- Creación
	- Objetos
	- Bindings
- Referencias a variables
- Desactivación y reactivación de bindings
- Eliminado
	- Objetos
	- Bindings

El tiempo entre la creación y eliminación de un elemento