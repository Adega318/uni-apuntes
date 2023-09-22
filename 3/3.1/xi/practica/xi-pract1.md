Comenzamos con una secuencia de bits que es enviada al modulador. El modulador la convierte en una señal a trasmitir y la envía al canal. El canal la modifica en función del ancho de banda (h(t)), tras eso se le añade ruido. El resultado sera r(t), señal recibida.

# Modulación
La secuencia de bits de **L** tamaño y la forma de pulso de longitud **N** (periodo símbolo), que siempre debe de ser par. El pulso al trasmitir un 0 es positivo y negativo al trasmitir un 1.

## Ejemplos
La construcción de la señal se basa en aplicar pulsos positivos y negativos.

Para 0 1 0 0 seria 1 -1 1 1

Los pulsos en octave son dos vectores, x e y, donde x es N e y es m y controla positivo y negativo.

Para 0100 en octave seria con N = 2:
{1 1, -1 -1 ,1 1 ,1 1}


necesitas un ejexS= 0:(L*N)-1