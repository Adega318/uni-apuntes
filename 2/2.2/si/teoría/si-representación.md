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
- Wumpus adyacente (sabe la casilla)
- Fosa adyacente (sabe la casilla)
- Oro en su casilla
- Choque al caminar a la pared
- Muerte de un Wumpus
## Actuadores
- Disparar
- Salir por (1,1)
- Coger/Soltar oro de su casilla
- Moverse