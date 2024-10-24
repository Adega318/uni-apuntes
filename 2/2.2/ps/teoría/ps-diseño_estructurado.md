# Características
- Simplifica el problema
- Ofrece estrategias
- Criterios de evaluación

# Diagrama de Estructura (DEC)
## Elementos
### Módulos
Un módulo es aquella parte del código que se puede llamar.
#### Visiones
- externa, visión desde el alto nivel con las entradas y salidas.
- interna, visión de bajo nivel centrada en la forma

### Comunicación y conexión
Indica la relación con otros módulos del sistema, habiendo dos señales de comunicación:
- Datos, datos crudos.
- Flags, señales de comunicación (bool).
## Nomenclatura
### Notación

![[Pasted image 20230313134059.png]]

### Ejemplo

![[Pasted image 20230430111031.png]]

# Tabla de interfaz
Complementa al diagrama de estructuras clarificando los flags y datos.
## Tipos

![[Pasted image 20230313135207.png]]

## Ejemplo

![[Pasted image 20230313135223.png]]

# Estrategias de diseño
Se parte de los DFD de último nivel sobre los que se aplican estrategias:
## Transformación
Se aplica sobre los DFD con uno o varios caminos de entradas que son transformadas a un formato que en el núcleo es transformado en el resultado que pasa a uno o varios caminos de salida donde se pasa al formato externo.

![[Pasted image 20230313135959.png]]

El análisis tiene los siguientes pasos:
1. Revisar el modelo
2. Determinar las características
3. Aislar el centro de transformación
	- burbujas que hacen la función central del DFD
4. Realizar un primer nivel de factorización
	- El primer nivel de factorización es la invención de módulos para coordinar las distintas zonas (entrada, centro y salida).
5. Realizar un segundo nivel de factorización
	- Expandimos sobre los módulos coordinadores para representar los procesos.
6. Refinar arquitectura
	- Se refinará la arquitectura comprobando si los módulos de la primera factorización son necesarios.
	- Cambios en los módulos con uniones o divisiones.
	- Añadir los flujos de datos.
7. Revisar
	- Se revisa en busca de errores.

![[Pasted image 20230430112232.png]]

## Transacción
Se aplica en DFD con un camino de entrada y camino de acción inicial que se divide en varios caminos de acciones independientes que llevan a su propio resultado.

![[Pasted image 20230313140026.png]]

Tiene los siguientes pasos de análisis, las dos primeras partes y dos ultimas son idénticas:
3. Identificar el centro de transacción
	- identificar el centro de la transacción, lugar donde se hace la separación.
4. 1º nivel de factorización

![[Pasted image 20230430112728.png]]

5. 2º nivel de factorización
	- en este segundo nivel se establece los flujos de datos.

# Tags
#2- 
#2-2 
#ps