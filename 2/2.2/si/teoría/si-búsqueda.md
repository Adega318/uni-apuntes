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

## Solución de problema de búsqueda
Secuencia de acciones que lleva a un estado meta, siendo la solución optima la que dentro del espacio de soluciones tiene el menor costo.
Para hallar una solución se debe explorar el espacio de estados con:
- criterio de selección y aplicación
- capacidad de decisión
- búsqueda simétrica

# Proceso de Búsqueda
## Estrategia de exploración
Las estrategias pueden ser diferentes y variadas
- Básica 1, sistemática sin nuevos estados.

![[Pasted image 20230217210324.png]]
![[Pasted image 20230516181426.png]]

- Básica 2, sistemática con eliminación.

![[Pasted image 20230217210427.png]]
![[Pasted image 20230516181451.png]]

- Básica 3, sistemática con eliminación de acciones y estados.

![[Pasted image 20230217210450.png]]
![[Pasted image 20230516181507.png]]

- Básica 4, sistemática con exploración (garantiza solución).

![[Pasted image 20230217210503.png]]
![[Pasted image 20230516181536.png]]

# Estrategias de búsqueda
## Características
### Dirección
Tenemos dos acercamientos a la dirección de la búsqueda de los estados iniciales a la meta o de la meta al estado inicial.
### Topología
Por la construcción de estados a partir de estados iniciales formando un árbol de búsqueda, creando árboles en el caso de que no haya convergencia o grafos, en el caso de los grafos se producen caminos redundantes. Esto lleva a que la exploración de árbol sea computacionalmente eficiente y ineficiente en memoria y la de grafo lo contrario.
#### Selección de acciones
Se busca en las acciones cuales son las posibles, en caso de que varias sean posibles se toman los siguientes criterios:
1. Evitar reutilizar acciones.
2. Priorizar nuevos estados.
3. Primero las de condiciones más restrictivas.

### Heurística
Función que nos permite estimar la calidad de una acción que nos permite optimizar la búsqueda. Para el algoritmo de $A^*$ la heurística siempre de ve de ser menor al coste real (admisible) y se debe cumplir a su vez $h(n)-h(n^{\prime}) <=c(n,a,n^{\prime})$ esto se entiende como que la estimación desde n debe de ser menor a la estimación desde $n^{\prime}$ más el coste de pasar de n a $n^{\prime}$ (consistente).
## Implementación
### Reconstrucción de la solución

![[Pasted image 20230426182001.png]]

La reconstrucción es el retroceso desde un final de camino hacia un estado anterior con caminos potencialmente válidos. Esto se puede aplicar únicamente a algoritmos con memoria de los caminos recorridos.
### Función sucesores

![[Pasted image 20230426182252.png]]

Lleva a cabo la expansión de un nodo, aplicando acciones y comprobando la meta.
### Listas
Se almacenan los nodos en dos listas:
- Abiertos, nodos a explorar.
- Cerrados, nodos ya explorados.

### Estructuras de datos
##### Nodos
Para este tipo de algoritmos podemos de una estructura de datos basada en estados almacenados en nodos interconectados.

![[Pasted image 20230217210909.png]]

##### Listas
Podemos hacer la implementación por listas, creando una lista con frontera y explorados.
La frontera son los nodos a explorar y la de explorados almacena los nodos ya visitados.
Podemos gestionarlo con tres tipos de algoritmo de siguiente:
FIFO, LIFO, PR
#### Pseudocódigo

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

![[Pasted image 20230426183059.png]]

Se detiene el proceso de búsqueda si se encuentra una solución en vez de considerar todas las opciones.
### Coste uniforme

![[Pasted image 20230426183323.png]]

Se hace la búsqueda, pero no se devuelve la primera encontrada, se establece un orden de exploración basándonos en el coste (se exploran caminos potencialmente más eficientes), devolviendo la óptima.
## Profundidad

![[Pasted image 20230426183438.png]]

Alta velocidad, pero puede llevar a opciones ineficientes.

![[Pasted image 20230217211144.png]]

Con respecto a la implementación con listas, se utilizará una pila para la frontera, lo que permitirá que los elementos menos recientemente añadidos sean los primeros en ser explorados (los menos profundos).
### Limitada
Explora en profundidad, rindiéndose cuando el camino supera una profundidad.
### Iterativa
Es una exploración limitada pero en ved de rendirse agota todas las opciones en esa profundidad y luego prospera a la siguiente.
## Complejidad

![[Pasted image 20230217211221.png]]

# Búsqueda informada
## Preferente por el mejor
Para establecer los estados más favorables es determinado por la función heurística h(n).
Función heurística: convierte un estado en un valor numérico.
### Avara

![[Pasted image 20230426184001.png]]

La búsqueda avara es la que siempre elige el nodo más prometedor en h(n) sin tener en cuenta el coste, siendo la frontera una cola de prioridad atendiendo a h(n).

![[Pasted image 20230217211300.png]]

### A*
La búsqueda A* toma en cuenta la perspectiva de la acción y el coste del camino.
- g(n), coste del mejor camino para alcanzar n.
- h(n), coste estimado de n a la meta.
- f(n)=g(n)+h(n), coste estimado de la mejor solución.

![[Pasted image 20230426184441.png]]
![[Pasted image 20230426184537.png]]

Para el algoritmo de $A^*$ la heurística siempre de ve de ser menor al coste real (admisible) y se debe cumplir a su vez $h(n)-h(n^{\prime} <=c(n,a,n^{\prime})$ esto se entiende como que la estimación desde n debe de ser menor a la estimación desde $n^{\prime}$ más el coste de pasar de n a $n^{\prime}$ (consistente).
## Local
### Escalada
Elige el mejor de los sucesores basándose en la heurística, siempre que los sucesores sean mejores que el padre.
- Cresta, región de estados mejores pero a los que no podemos llegar con movimientos simples.
- Mesetas, región donde varios estados tienen el mismo valor en un paso simple.

# Tags
#2- 
#2-2 
#si