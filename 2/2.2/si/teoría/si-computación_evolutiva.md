# Selección
## Ciclos de generaciones
Se hace la selección de los mejores individuos y algunos peores, esto se puede hacer por:
- Ruleta, se sortean N huecos entre los individuos con probabilidades proporcionales a su desempeño.
- Torneo, se seleccionan N al azar y  se escoge el mas apto.

![[Pasted image 20230503124624.png]]

## Cruce
Mezcla de los seleccionados de la generación, con varios tipos:
- Puntos, tomar alternativamente fragmentos de genes de los seleccionados.
- Uniforme, se elige aleatoria mente por cada gen de que seleccionado tomar herencia.
	- Mascara, genes a elegir de cada uno pre fijados.

El cruce aumenta la homogeneidad.
## Mutación
Generación de valores para los genes, clasificándose en:
- Bit, un bit aleatorio cambia.
	- Multibit, varios bits cambian.
- Gen, mutación del valor del gen (valor con muchos posibles valores).
	- Multigen, varios genes cambian.
- Intercambio, intercambio de los valores de dos genes.
	- Barajado, re organización de varios genes.

La mutación la diversidad.

# Sustitución
Para mantener el numero fijo de población se deben sustituir los individuos de la población, con tres tipos de sustitución en base a su evaluación:
- Peores, se eliminan los peores de la población.
- Padres, se eliminan los padres.
- Parecidos, se eliminan los similares.

## Steady-state
### Cruce

![[Pasted image 20230503132427.png]]

Selecciono de 2 individuos, se cruzan evalúan y ordenan, eliminando los dos peores para hacer hueco.
### Mutación

![[Pasted image 20230503132532.png]]

Se selecciona uno, se muta, evalúa y ordena.
# Función de evaluación

# Criterios de paro
Criterios para la parada del entrenamiento, 
## Criterios sobre parámetros
Tamaño de población, aspecto de gran importancia en el costo comunicacional y vital para evitar la homogeneizacion.
- balance entre pequeña y grande.
- población de tamaño constante o variable.

Porcentaje de cruce y mutación
# Tags
#2- 
#2-2 
#si 