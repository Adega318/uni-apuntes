# Introducción
El comportamiento deseado para el sistema es representado mediante una evaluación sobre los resultados generados sobre el entorno, esto permite que el sistema aprenda mediante un proceso de prueba y error con el entorno y refuerzo/penalización de aciones. La formalización del problema:
$\Pi : S\rightarrow A$
$V^{\pi}(S_{t})=\sum\limits_{i=0}^{\infty}y^{i}r_{t+1}$
- $V^{\pi}(S_{t})$, función de refuerzo acumulado al aplicar la política $\Pi$ al estado $S_{t}$.
- $y$, constante que determina la importancia de las recompensas actuales frente a las futuras, valores cercanos a 0 hacen el sistema miope y cercanos al 1 precavido.

# Elementos
Los elementos principales en el aprendizaje por refuerzo son:
- Agente, sujeto de aprendizaje.
- Entorno, mundo sobre el que actúa el agente.
- Política, define el comportamiento del agente, estableciendo los estados y aciones.
- Función de refuerzo, establece recompensa para aciones beneficiosas y penalizaciones para erróneas.
- Función de acción-valor, establece recompensas a largo plazo para el agente.
- Modelo de entorno (opcional), método para conocer el próximo estado dada una acción y estado actual.

# Procesos de Decisión de Markov
Muchos de los algoritmos de aprendizaje por refuerzo son dependientes de cumplir la **Propiedad de Markov**, en la que se estipula que la evolución del entorno es únicamente dependiente del estado y acción tomada. A un problema de aprendizaje donde el entorno cumple la propiedad ya mencionada es denominado como **Proceso de Decisión de Markov (MDP)**, cuando el espacio de estados y acciones es finito se dice que es **Procesos de Decisión de Markov finito**.
Los MDP son definidos con <S,A,T,R> donde:
- S, estado actual.
- T, función de transición.
- R, función de refuerzo.

# Taxonomía de métodos
Los métodos de resolución en un problema de aprendizaje reforzado se pueden clasificar en función del conocimiento que se tenga del modelo:
- Resolución a partir de un conocimiento completo, estados y acciones son conocidos.
- Resolución a partir de un conocimiento incompleto, estados y acciones son parcialmente conocidos.

Es importante encontrar la inferencia de acción-valor óptima $Q(s, a)$, donde se expresa el refuerzo correspondiente a una acción en un estado.
# Exploración y explotación
Una de las principales complicaciones es el equilibrio entre la exploración y explotación, una de las maneras de conseguir dicho equilibrio es realizar una exploración favoreciendo progresivamente la explotación.
# Q-learning
Proceso de aprendizaje con conocimiento incompleto basado en la actualización de la tabla $Q(s, a)$, en caso de ser un MDP se sabe que se llegara a la tabla óptima.
$Q(s,a)\leftarrow Q(s,a)+\alpha\cdot[r+y\cdot \max\limits_{b}Q(s',b)\cdot Q(s,a)]$
- $\alpha$, relación de importancia entre antiguas y nuevas estimaciones.