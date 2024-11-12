# Funcionamiento
El sistema encajará los siguientes tags:
- wordUc, conjunto de caracteres en mayúsculas.
- wordLc, conjunto de caracteres en minúsculas.
- number, números con decimales y negativos opcionales.
- word, palabra genérica.
- separataor, espaciadores y saltos de línea.
- puntuation, el punto.
Con los anteriores se crean los encajes para los diferentes tipos de palabras (contado de palabras) y las mismas con símbolo de puntuación seguido de separador (contado de frases).
Los contadores de los encajes anteriores son impresos tras finalizar la lectura.
# Consideraciones
1. Decimales, los decimales están considerados mediante el uso de ',' y el uso de un número seguido de una ',' no es considerado como decimal sino como dos palabras.
2. Puntos, los puntos pueden aparecer en palabras sin comenzar una nueva frase siempre y cuando no estén seguidos de un separador.
3. 