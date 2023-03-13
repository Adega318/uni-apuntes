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
Indica la relación con otros módulos del sistema.
## Nomenclatura
### Notación
![[Pasted image 20230313134059.png]]
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
El analisiss es:
1. Revisar el modelo
2. Determinar las caracteristicas
3. Aislar el centro de transformación
4. Realizar un primer nivel de factorización
5. Realizar un segundo nivel de factorización
6. Refinar arquitectura
7. revisar
## Transacción
Se aplica en DFD con un camino de entrada y camino de acción inicial que se divide en varios caminos de aciones independientes que llevan a su propio resultado.
![[Pasted image 20230313140026.png]]
# Tags
#2- 
#2-2 
#ps