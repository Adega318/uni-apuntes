Las redes autoorganizativas son basadas en nodos y un modelo de aprendizaje no supervisado, basándose en reglas para la puntuación de los resultados.
Este proceso de entrenamiento automático produce patrones.
- Patrón, entidad representada por un conjunto de propiedades y relaciones entre ellas.

# Mapas autoorganizativos

![[Pasted image 20230518200704.png]]

Los mapas autoorganizativos son redes donde cada nodo contiene sus pesos y una posición en el mapa, permitiendo la representación de localidad de las neuronas. Estas redes no son supervisadas y aprenden mediante aprendizaje competitivo, los nodos compiten por modificar sus pesos, ganado solo uno.
## Kohonen (SOM)
Los mapas de kohonen agrupan los datos de entrada similares, especializando las neuronas creando clusters.

La capa de entrada recibe los datos.
- Las neuronas de entrada reciben los datos y los distribuyen entre todas las competitivas (no tiene comunicación entre si).
- El vector de pesos de cada neurona de la capa de competición tendrá el mismo nº de componentes que el vector de entrada.
	- Por tener la misma dimensión se pueden comparar entre si con una función de distancia.
- La distancia utilizada suele ser la euclídea, con la salida de la competición siendo calculada por esa distancia.
$\tau_{j}=$ salida de la neurona j
$e_{i}=$entrada i
$\mu_{ij}=$peso de $e_{i}$ de la neurona j$$\tau_{j}=\sqrt{\sum_{i=1}^{n}(e_{i}-\mu_{ij})^{2}}$$
### Funcionamiento
#### Aprendizaje
Proceso de aprendizaje y entrenamiento de la red.
- Pesos inicializados aleatoria mente.
- Se introducen patrones calculando las salidas de la capa de competencia.
- La neurona con menor distancia con ese vector de entrada obtendrá salida 1 y el resto 0.
- El pedos de la ganadora se modifica junto de sus vecinas en función del radio de vecindad.
	- la vecindad es la distancia entre neuronas, se modifica con el tiempo, estabilizando a lo largo del aprendizaje.
-  Vecindad, indica las células que aprenden por proximidad a la vencedora de la competición.
	- Radio, distancia de las neuronas consideradas vecinas.
	- Topologia, neuronas consideradas vecinas.
	- Función, cuantifica lo vecina que es una neurona.

Función de entrenamiento:
$\alpha=$ tasa de aprendizaje
$e_{i}=$ entrada i
$\mu_{ij}=$ peso de $e_{i}$ de la neurona j
$d()=$ función de vecindad
$c_{i}=$ célula ganadora
$c_{j}=$ célula vecina$$\Delta\mu_{ij}=\frac{\alpha}{d(c_{i},c_{j})}(e_{i}-\mu_{ij})$$
La vecindad puede ser modificar con el tiempo del entrenamiento permitiendo controlar la velocidad de aprendizaje y estabilidad del mismo.

El algoritmo de aprendizaje será el siguiente:
1. Inicializar pesos
2. Presentar una entrada
3. Propagar el patrón de entrada hasta la capa de competición
4. Selección de la neurona ganadora
5. Actualizar las conexiones de ganador y vecinos
6. Comprobar criterios de parada y regresar al 2

#### Validación
Repetición del proceso de entrenamiento n veces con configuraciones iniciales diferentes para validad la calidad del SOM y ayudar en el calculo del error de cuantización medio.
- Error de cuantización medio, evalúa el grado de adaptación del mapa SOM a los datos de  entrada, siendo mejor el que menor error obtenga entre las conexiones de las BMU y los  vectores (patrones de entrada) a los que representa.
$N=$ numero de vectores de entrada.$$E=\frac{1}{N}\sum_{i=1}^{N}||ei-w_{bmu}||^{2}$$
- Medidas de prevención de la topología, medidas para evaluar la calidad de la distribución de las neuronas, buscando la cercanía de neuronas con activación sobre entradas similares.
#### Operación
- Patrón inicial para conocer el prototipo
- Calculo de similitud de las neuronas
- Vencedor con mayor similitud

#### Representación geométrica
La representación de los mapas se basa en el establecimiento de coordenadas usando los pesos de las neuronas.
#### Aplicaciones
Las principales aplicaciones son:
- Agrupación de las entradas
- Análisis de componentes principales
# Crecimiento de redes
El paradigma de crecimiento de redes se centra en la creación de redes con arquitecturas ajustables en base a los datos, permitiendo la creación de modelos simplificados con preservación de la topología.
## Inserción de neuronas
Para la inserción de neuronas se determina la localización y conexiones con el **valor resourze**, valor asignado a cada neurona para medir su distancia con la estructura ideal. Tras una cantidad de ciclos se consideraran los valores resource para hacer la inserción y posición de inserción.
## Borrado de neuronas
Neuronas con pesos despreciable se eliminan al no tener efecto sobre la red.
## Estructuras crecientes (GCS)
Las estructuras GCS se basa en el mantenimiento de las neuronas de entrada y salida con la modificación de las capas ocultas.
Se establecen estructuras para una cantidad K de nodos:

![[Pasted image 20230424131752.png]]

El entrenamiento de estas redes en competitivo con vecindad directa y un contador de su error de cuantización.
### Aplicación
Las aplicaciones de este tipos de redes es la clasificación de los datos.
## Gas neuronal creciente (GNS)
Este modelo a diferencia del GCS es un modelo donde no se mantiene ninguna estructura, adaptándose a las diferentes dimensiones.

![[Pasted image 20230518212440.png]]

Esta adaptación llevan a que llene  los espacios con neuronas (como un gas).
# Tags
#2- 
#2-2 
#si 