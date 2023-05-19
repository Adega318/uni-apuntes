
![[Pasted image 20230508133850.png]]

# Algoritmos genéticos

![[Pasted image 20230508135107.png]]

Los algoritmos genéticos son algoritmos de búsqueda inspirados en la naturaleza, mezclando los más aptos e introduciendo mutaciones a la población.
## Componentes
Los algoritmos genéticos tiene los siguientes componente:
1. Representación vectorial de las soluciones.
2. Método de creación de poblaciones iniciales.
3. Función de evaluación.
4. Operadores genéticos.
5. Valores de parámetros.

## Población y evaluación de individuos
La población inicial es aleatoria, a cada individuo de la población se le evaluará asignando una puntuación para cada uno.
## Ciclos de generaciones
### Criterio de selección
Selección  de los individuos a cruzar para la siguiente generación, habiendo varios tipos de selecciones:
- Ruleta, se sortean N huecos entre los individuos con probabilidades proporcionales a su desempeño.
- Torneo, se seleccionan N al azar y  se escoge el mas apto.

![[Pasted image 20230503124624.png]]

### Cruce
Mezcla de los seleccionados de la generación, con varios tipos:
- Puntos, tomar alternativamente fragmentos de genes de los seleccionados.
- Uniforme, se elige aleatoria mente por cada gen de que seleccionado tomar herencia.
	- Mascara, genes a elegir de cada uno pre fijados.

El cruce aumenta la homogeneidad.
### Mutación
Generación de valores para los genes, clasificándose en:
- Bit, un bit aleatorio cambia.
	- Multibit, varios bits cambian.
- Gen, mutación del valor del gen (valor con muchos posibles valores).
	- Multigen, varios genes cambian.
- Intercambio, intercambio de los valores de dos genes.
	- Barajado, re organización de varios genes.

La mutación la diversidad.
### Sustitución
Para mantener el numero fijo de población se deben sustituir los individuos de la población, con tres tipos de sustitución en base a su evaluación:
- Peores, se eliminan los peores de la población.
- Padres, se eliminan los padres.
- Parecidos, se eliminan los similares.

### Steady-state
#### Cruce

![[Pasted image 20230503132427.png]]

Selecciono de 2 individuos, se cruzan evalúan y ordenan, eliminando los dos peores para hacer hueco.
#### Mutación

![[Pasted image 20230503132532.png]]

Se selecciona uno, se muta, evalúa y ordena.
## Función de evaluación
La función de evaluación debe de ser capaz de evaluar los individuos penalizándolos y recompensándolos.
## Criterios de parada
Criterios para la parada del entrenamiento, pudiendo ser un número de ciclos, error mínimo, ...
### Criterios sobre parámetros
Tamaño de población, aspecto de gran importancia en el costo comunicacional y vital para evitar la homogeneizacion.
- balance entre pequeña y grande.
- población de tamaño constante o variable.

Porcentaje de cruce y mutación
- cruce de 0.9 y mutación de 0.05-0.1
- valores variables durante el algoritmo, comienzan muy cruzado y aumenta la mutación con el tiempo.
# Red de neuronas artificiales (RNA)

![[Pasted image 20230519152654.png]]

Conjunto de neuronas que operan las entradas para obtener la salida deseada.
## Recurrente

![[Pasted image 20230519152840.png]]

La conectividad de los nodos en este tipo de red es total, descartando el concepto de capas. Este tipo de distribuciones tiene uso en tareas de reconocimiento, predicción y asociación de secuencias. Su aprendizaje es complicado y lento.
## Entrenamiento supervisado
El entrenamiento supervisado de estos modelos se vasa en el ajuste de pesos para la reducción del error entre la salida y el resultado esperado.
## Bloques constructivos

![[Pasted image 20230519153901.png]]

## Diseño RNA
1. Entrenamiento, búsqueda de los  pesos óptimos.
2. Topología, busqueda del numero de neuronas 
# Tags
#2- 
#2-2 
#si 