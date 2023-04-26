# Agentes solucionadores
## Etapas
- Formular las metas, definición de los estados de victoria y derrota.
- Formular el problema, representar de manera abstracta el problema basado en estados y acciones posibles.
- Búsqueda, encontrar las soluciones óptimas basándose en la formulación.
- Ejecución, efectúa las acciones determinadas en la solución obtenida en la búsqueda.
## Problemas de búsqueda
Compuestos por:
1. Estado inicial, representación de los posibles estados.
2. Conjunto de acciones, para los estados las acciones posibles.
3. Modelo de transición, asociación de las posibles acciones con otros estados.
4. Prueba de meta, establecimiento de la comprobación de meta.
5. Función de coste del camino, función de calculo del coste del camino a partir de las acciones tomadas.
# Proceso de Búsqueda
## Estrategia de exploración
Las estrategias pueden ser diferentes y variadas
- Básica 1, sistemática sin nuevos estados.
![[Pasted image 20230217210324.png]]
- Básica 2, sistemática con eliminación.
![[Pasted image 20230217210427.png]]
- Básica 3, sistemática con eliminación de acciones y estados.
![[Pasted image 20230217210450.png]]
- Básica 4, sistemática con exploración (garantiza solución).
![[Pasted image 20230217210503.png]]
# Estrategias de búsqueda
## Generales
Aplicables a todos los problemas con menor eficiencia.
## Especifico
Requieren de conocimiento del problema otorgando mayor eficiencia.
## Características
### Dirección
Se consideran dos direcciones, de los estados iniciales a los estados meta (proceso progresivo) o de los estados meta a los estados iniciales (proceso regresivo).
### Topología
### Criterios de selección
### Optimización de la búsqueda
## Implementación
### Reconstrucción de la solución
La reconstrucción es el retroceso desde un final de camino hacia un estado anterior con caminos potencialmente válidos. Esto se puede aplicar únicamente a algoritmos con memoria de los caminos recorridos.
### Estructuras de datos
#### Nodos
Para este tipo de algoritmos podemos de una estructura de datos basada en estados almacenados en nodos interconectados.
![[Pasted image 20230217210909.png]]
#### Listas
Podemos hacer la implementación por listas, creando una lista con frontera y explorados.
La frontera son los nodos a explorar y la de explorados almacena los nodos ya visitados.
Podemos gestionarlo con tres tipos de algoritmo de siguiente:
FIFO, LIFO, PR
### Pseudocódigo
![[Pasted image 20230217211014.png]]
## Evaluación
### Completitud
Esta métrica determina la solución proporcionada y si es siempre proporcionada.
### Complejidad
La complejidad tanto computacional como la del propio código.
### Optimización
Los requisitos de memoria de la solución.
### Coste
El coste es el coste de búsqueda y coste de camino.
# Búsquedas no informadas
## Amplitud
Se exploran al mismo tiempo todos los caminos, siempre se encuentra la solución más óptima, sus requerimientos de memoria y tiempo con altos.
![[Pasted image 20230217211105.png]]
Con respecto a la implementación con listas, se usará una cola para la frontera, lo que permitirá que los elementos menos recientemente añadidos sean los primeros en ser explorados (los menos profundos).
### Prioridad
Se detiene el proceso de búsqueda si se encuentra una solución en vez de considerar todas las opciones.
### Coste uniforme
Se hace la búsqueda, pero no se devuelve la primera encontrada, se establece un orden de exploración basándonos en el coste (se exploran caminos potencialmente más eficientes), devolviendo la óptima.
## Profundidad
Alta velocidad, pero puede llevar a opciones ineficientes.
![[Pasted image 20230217211144.png]]
Con respecto a la implementación con listas, se utilizará una pila para la frontera, lo que permitirá que los elementos menos recientemente añadidos sean los primeros en ser explorados (los menos profundos).
### Limitada
Explora en profundidad, rindiéndose cuando el camino supera una profundidad.
### Iterativa
## Complejidad
![[Pasted image 20230217211221.png]]
# Búsqueda informada
## Preferente por el mejor
Para establecer los estados más favorables es determinado por la función heurística h(n).
Función heurística: convierte un estado en un valor numérico.
## Avara
La búsqueda avara es la que siempre elige el nodo más prometedor en h(n) sin tener en cuenta el coste.
La frontera será una cola de prioridad atendiendo a h(n).
![[Pasted image 20230217211300.png]]
## A*
La búsqueda A* toma en cuenta el h(n) y el coste para tomar las decisiones.
La heurística dará la solución adecuada si se cumple que se subestima el coste real.
## Local
### Escalada
Elige el mejor de los sucesores basándose en la heurística, siempre que los sucesores sean mejores que el padre.
- Cresta, región de estados mejores pero a los que no podemos llegar con movimientos simples.
- Mesetas, región donde todos los estados tienen el mismo valor en un paso simple.
# Tags
#2- 
#2-2 
#si