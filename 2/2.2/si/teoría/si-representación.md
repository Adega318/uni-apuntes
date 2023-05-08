# Agentes basados en conocimiento
Son agentes que constan de una base de conocimiento. Esto hace que su base de conocimiento sea vital para la toma de decisiones.
# Mundo wumpus
Problema de agentes inteligentes con formato de juego.
## Medida de rendimiento
- 1000 salir con oro
- -1000 morir
- -1 por ación
- -10 por flecha

## Entorno
- Tablero de 4x4
- Agente en (1,1)
- Posiciones de los elementos aleatoria
- Probabilidad de cuadrado con fosa 0.2

## Sensores
- Wumpus adyacente (no sabe la casilla)
- Fosa adyacente (no sabe la casilla)
- Oro en su casilla
- Choque al caminar a la pared
- Muerte de un Wumpus

## Actuadores
- Disparar
- Salir por (1,1)
- Coger/Soltar oro de su casilla
- Moverse

# Lógica
## Generalidades
- Sintaxis, define sentencias en el lenguaje.
- Semántica, define el significado de las sentencias.
- Implicaciones, relaciones lógicas entre sentencias.

## Modelos
Los modelos son los posibles estados del entorno, donde se pueden evaluar sentencias.
## Inferencia lógica
Es el proceso de evaluar sobre los modelos posibles por las percepciones, una sentencia (ver los modelos que salen de una acción).
# Lógica proposicional
Permite definir cualquier cosa para la que existe un procedimiento completo y sólido.
## Sintaxis
- Las proposiciones son binarias.
- Sentencias atómicas o complejas

## Semántica
- Relaciones entre las proposiciones y sentencias.

# Inferencia
## Métodos estructurados
### Redes semánticas
Redes de relaciones entre conceptos.
### Frames
Son relaciones con niveles escalonados, un buen ejemplo es el índice de un libro.
#### Demons
Los demons son sistemas de actualización y ejecución para los frames.
#### Tipos
- Descriptivos, frame centrado en la muestra de datos.
- Control, frame centrado en la especificación de los formatos de datos.

### Reglas de producción
Tenemos tres tipos de reglas:
- if, condición o premisa.
- then, conclusión.
- else, alternativa.

#### Tipos
- ifall, todas las cláusulas cumplen.
- ifany, alguna cláusula cumple.
- ifsome, se comprueban todas y luego se hace ifany.

# Tags
#2-
#2-2 
#si