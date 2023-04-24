# Autoorganizativas
Es la modificación repetida de los pesos de las conexiones en respuesta a nodos de activación siguiendo reglas preestablecidas.
## Mapas autoorganizativos
Se mapea la red para establecer zonas que de excitación en función del tipo de entradas, viendo las funciones de las parte de la red y creando categorías de patrones.
### Kohonen
Kohonen se basa en el aprendizaje no supervisado donde las neuronas experiencia aprendizaje competitivo donde la neurona ganadora es la actualizada, creando clusters.
- vecindad, preserva las relaciones topologicas, neuronas cercanas responden de manera similar.
La capa de entrada recibe señales de entrada de la red.
- Dimensión, la entrada depende del número de atributos que tengan los patrones de entrada, si n atributos -> e={e1, ..., en}
- Todas las neuronas de la capa de entrada se conectan con todas de la de competición.
- Con m neuronas en la capa de competición, los pesos de conexión se definen en una matriz (n,m).
- El vector de pesos de cada neurona de la capa de competición tendrá el mismo nº de componentes que el vector de entrada.
	- Por tener la misma dimensión se pueden comparar entre si con una función de distancia.
- 
$\tau_{j}=$ salida de la neurona j
$e_{i}=$entrada i
$\mu_{ij}=$peso de $e_{i}$ de la neurona j
$$\tau_{j}=\sqrt{\sum_{i=1}^{n}(e_{i}-\mu_{ij})^{2}}$$
### Aprendizaje
Proceso de aprendizaje y entrenamiento de la red.
Función de entrenamiento:
$\alpha=$ 
$e_{i}=$ entrada i
$\mu_{ij}=$ peso de $e_{i}$ de la neurona j
$d()=$ función de vecindad
$c_{i}=$ célula ganadora
$c_{j}=$ célula vecina
$$\Delta\mu_{ij}=\frac{\alpha}{d(c_{i},c_{j})}(e_{i}-\mu_{ij})$$
### Operación
# Crecimiento de redes
Tras un numero constante de modificaciones de los pesos se hace el re-calculo de las neuronas con las modificaciones necesarias.
## Inserción de neuronas
La adición se produce en los clusters, los pesos de las neuronas generadas se calculan en base a las vecinas.
## Borrado de neuronas
Neuronas con pesos despreciable se eliminan al no tener efecto sobre la red.
## Estructuras crecientes (GCS)

# Tags
#2- 
#2-2 
#si 