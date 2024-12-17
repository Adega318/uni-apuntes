Existen dos principales tipos de tipado:
- Fuerte, tipado donde se impide la aplicación de operaciones a tipos con los cuales las mismas no son compatibles.
- Estático, tipado donde el compilador hace todas las comprobaciones en tiempo de compilación.

# Sistemas de tipado
En los sistemas te tipados tenemos principalmente los siguientes tipos:
- Directos
	- Integer
	- Boleano
	- Char
	- Enumeración
	- Subrange
- Escalares
	- Discretos
	- Reales
- Compuestos
	- Records
	- Arrays
	- Sets
	- Pointers
	- List
	- Files

Uno de los puntos a buscar en un sistema de tipado es la **orthogonality**, lo que se refiere a la capacidad de combinar los términos sin restricciones.
## Comprobación de tipo
Los sistemas de tipo tienen las siguientes comprobaciones:
- Equivalencia, comparación de igualdad entre dos tipos o valores.
	- Nombre, equivalencia basada en la declaración.
	- Estructura, equivalencia basada en la estructura bajo la declaración.
- Compatibilidad, comprobación de la capacidad de uso de un tipo A donde se pide un tipo B.
- Inferencia, búsqueda del tipo de una expresión basándose en el de sus operandos. 

En la comprobación de tipos se puede dar la **coerción**, donde se cambia el tipo de uso de los términos para realizar una operación (suma de un float y un int, se coacciona el int a float).

# Records y Variantes

# Array
Tipo compuesto, normalmente homogéneo, el cual es equivalente a un mapeo de índice valor.
- Tiempo de vida global y forma estática, si la forma es conocida en tiempo de compilación y el array puede existir durante la duración del programa, el compilador le asignará memoria global.
- Tiempo de vida local y forma estática, con una forma estática, pero con incapacidad de existir durante todo el programa, se le asignará un stack en tiempo de ejecución.

Estos almacenamientos se pueden hacer de dos principales maneras, 
- Elementos continuos, se toma un array NxM y se compone como un array de N elementos, los cuales son arrays de M elementos.
- Punteros de fila, bueno para el almacenamiento de arrays de alto tamaño al quitar la necesidad de segmentos continuos de alto tamaño.

## Strings
Stings suelen ser arrays de caracteres con una denotación particular.
# Sets
