# Autoorganizativas
Es la modificación repetida de los pesos en respuesta a nodos de activación.
## Mapas autoorganizativos
Se mapea la red para establecer zonas que de excitación en función del tipo de entradas, viendo las funciones de las parte de la red y creando categorías de patrones.
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
## Inserción de neuronas

## Borrado de neuronas