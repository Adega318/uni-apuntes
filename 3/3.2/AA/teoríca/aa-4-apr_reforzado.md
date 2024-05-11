# Introducción
El comportamiento deseado para el sistema es representado mediante una evaluación sobre los resultados generados sobre el entorno, esto permite que el sistema aprenda mediante un proceso de prueba y error con el entorno y refuerzo/penalización de aciones. La formalización del problema:
$\Pi : S\rightarrow A$
$V^{\pi}(S_{t})=\sum\limits_{i=0}^{\infty}y^{i}r_{t+1}$
- $V^{\pi}(S_{t})$, función de refuerzo acumulado al aplicar la política $\Pi$ al estado $S_{t}$.
- $y$, constante 
# Elementos
Los elementos principales en el aprendizaje por refuerzo son:
- Agente, sujeto de aprendizaje.
- Entorno, mundo sobre el que actúa el agente.
- Política, define el comportamiento del agente, estableciendo los estados y aciones.
- Función de refuerzo, establece recompensa para aciones beneficiosas y penalizaciones para erróneas.
- Función de acción-valor, establece recompensas a largo plazo para el agente.
- Modelo de entorno (opcional).

# Procesos de Decisión de Markov

# Taxonomía de métodos de AR
# Q-learning