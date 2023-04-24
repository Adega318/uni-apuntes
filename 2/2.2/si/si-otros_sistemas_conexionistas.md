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
- La distancia utilizada suele ser la euclídea, con la salida de la competición siendo calculada por esa distancia.
$\tau_{j}=$ salida de la neurona j
$e_{i}=$entrada i
$\mu_{ij}=$peso de $e_{i}$ de la neurona j
$$\tau_{j}=\sqrt{\sum_{i=1}^{n}(e_{i}-\mu_{ij})^{2}}$$
### Aprendizaje
Proceso de aprendizaje y entrenamiento de la red.
- Pesos inicializados aleatoria mente.
- Se introducen patrones calculando las salidas de la capa de competencia.
- La neurona con menor distancia con ese vector de entrada obtendrá salida 1 y el resto 0.
- El pedos de la ganadora se modifica junto de sus vecinas en función de la vecindad.
	- la vecindad es la distancia entre neuronas, se modifica con el tiempo, estabilizando a lo largo del aprendizaje.

Función de entrenamiento:
$\alpha=$ tasa de aprendizaje
$e_{i}=$ entrada i
$\mu_{ij}=$ peso de $e_{i}$ de la neurona j
$d()=$ función de vecindad
$c_{i}=$ célula ganadora
$c_{j}=$ célula vecina
$$\Delta\mu_{ij}=\frac{\alpha}{d(c_{i},c_{j})}(e_{i}-\mu_{ij})$$
- Vecindad,
	- Radio, distancia de las neuronas consideradas vecinas.
	- Topologia, neuronas consideradas vecinas.
	- Función, cuantifica lo vecina que es una neurona.
### Validación
Repetición del proceso de entrenamiento n veces con configuraciones iniciales diferentes para validad la calidad del SOM y ayudar en el calculo del error de cuantización medio.
- Error de cuantización medio, evalúa el grado de adaptación del mapa SOM a los datos de  entrada, siendo mejor el que menor error obtenga entre las conexiones de las BMU y los  vectores (patrones de entrada) a los que representa.
$N=$ numero de vectores de entrada.
$$E=\frac{1}{N}\sum_{i=1}^{N}||ei-w_{bmu}||^{2}$$

### Operación
- Patrón inicial para conocer el prototipo
- Calculo de similitud de las neuronas
- Vencedor con mayor similitud
### Representación geométrica
### Aplicaciones
## SOM
Ventajas:
- Transpariencia
- Localidad de los datos
- Visualización graafica
- Integración en otras teccnicas
Desventaja:
- Necesisdad de arquitectura definida e invariable duante el entrenamiento.
- Neuronas superfluas
- No determinación 
# Crecimiento de redes
La redes de crecimiento se basan en la ampliación de las neuronas en zonas de alto peso y eliminación de las neuronas con pesos despreciables. Tras un numero constante de modificaciones de los pesos se hace el re-calculo de las neuronas con las modificaciones necesarias.
## Inserción de neuronas
Para la inserción de neuronas se considera el:
- Valor resource, valor variante que indica la distancia a la estructura ideal, calculado en la creación de neuronas.
Las nuevas neuronas tendrán sus pesos calculados en base a su vecinos.
## Borrado de neuronas
Neuronas con pesos despreciable se eliminan al no tener efecto sobre la red.
## Estructuras crecientes (GCS)
Las estructuras GCS se basa en el mantenimiento de las neuronas de entrada y salida con la modificación de las capas ocultas.
Se establecen estructuras para una cantidad K de nodos:
![[Pasted image 20230424131752.png]]
### Capa de salida
La capa de salida es idéntica a la de Kohonen.
- Error de cuantización, error almacenado de cada neurona con la distancia euclídea en su momento ganador.
# Tags
#2- 
#2-2 
#si 