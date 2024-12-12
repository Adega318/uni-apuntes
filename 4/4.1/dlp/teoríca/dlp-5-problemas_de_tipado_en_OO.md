# Comprobación de tipos
El subtipado y herencia dificultan el proceso de comprobación de tipos, esto lleva a menguar el tipado estático o la exigencia de cast para la indicación estática de tipos.
Estas características llevan a un sistema de tipado rígido, donde ciertas características de la orientación a objetos se ven limitadas.
# Cambio del tipo del resultado
El cambio en tipo producido por funciones como "clone" donde el tipo deseado de la salida es el tipo del objeto clonado, pero por las características del tipado estático es el tipo padre, esto es resuelto en distintos lenguajes con múltiples métodos:
- C++, uso de cast obligados para la indicación del tipo de salida.

# Métodos binarios
Los métodos binarios son métodos donde el tipo de uno de los parámetros es el mismo al del receptor del mensaje.