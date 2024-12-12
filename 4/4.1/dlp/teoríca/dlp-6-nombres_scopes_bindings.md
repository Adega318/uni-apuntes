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

El almacenamiento se divide en los siguientes métodos:
- Estática
	- Código
	- Globales
	- Variables estáticas
	- Constantes
- Pila
	- Parametros
	- Variables locales
	- Temporales
- Heap

# Scope
Sección de programa de tamaño máximo donde no hay cambio de binding o al menos no redeclaración.
Estos scopes tienen reglas que se les aplican:
- En salida
	- Eliminación de bindings locales
	- Reactivación de bindings desactivados en entrada
- Algol 68
	- Creación de bindings al entrar a un scope.
- Ada, reservado de espacio, arranque de tareas y errores propagados.

A la hora de definir los scope tenemos dos acercamientos, el clásico donde se establece basándose en la estructura léxica del código lo que permite la determinación del mismo por parte del compilador, por otro lado, tenemos la versión dinámica donde el scope depende el estado actual del programa.
- Estáticos, en un scope solo se consideran las variables globales e internas del scope.
- Dinámico, en un scope se consideran globales y las de los scope padre.