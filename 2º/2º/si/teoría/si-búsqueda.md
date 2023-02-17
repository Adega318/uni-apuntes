# Agentes solucionadores
## Etapas
- Formular las metas, definición de los estados de victoria y derrota.
- Formular el problema, representar de manera abstracta el problema basado en estados y acciones posibles.
- Búsqueda, encontrar las soluciones óptimas basándose en la formulación.
- Ejecución, efectúa las acciones determinadas en la solución obtenida en la búsqueda.
# Proceso de Búsqueda
## Estrategia de exploración
Las estrategias pueden ser diferentes y variadas
- Básica 1, sistemática sin nuevos estados
![[Pasted image 20230217210324.png]]
- Básica 2, sistemática con eliminación
![[Pasted image 20230217210427.png]]
- Básica 3, sistemática con eliminación de acciones y estados
- Básica 4, sistemática con exploración (garantiza solución)

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

Prea este tipo de algoritmos podemos de una estructura de datos basada en estados almacenados en nodos interconectados.

![](https://lh5.googleusercontent.com/z05ON9EULNnzpCg8uiE-TOcByqJuTSnZsk1JFyKWGRSU_A6QoxhueEDwynrkGuuZerkqXNNQQsVdVhdbBeen_B7wImxHPvEfEZBAn-i0di4W56gle0QVgWgRQ5Rtd66ewPxYGsS5j5kD3KhGRfQMBmU)

#### Listas

Podemos hacer la implementación por listas, creando una lista con frontera y explorados.

La frontera son los nodos a explorar y la de explorados almacena los nodos ya visitados.

Podemos gestionarlo con tres tipos de algoritmo de siguiente:

FIFO, LIFO, PR

### Pseudocódigo

![](https://lh3.googleusercontent.com/gy5dymib55HLvgnBmnIvKhNpNIrWZzc4sv_J-cve_Dzw382NBXcQHY1rpOcO20HAO76FPbMGzVDNfI7Bw_p_agzuwP9nMNWUtOzbHLqP3vZwHiyX1j_JA2aLc61Lh21qFRA0Ul-mgWAd74qVED8AsN4)

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

![](https://lh5.googleusercontent.com/nKf46JrOZKqM8iCCHZuyMSIQqQFvi4GvsAqiEMcKZuzsL-XscHEw-GNChX3R1qNZc_kd-CsUWuD1RwwCqVRAm0w07HfUXrnbphSyHCEvV6tRUuWNtZ5H8vbNIKqfiZ6xQOWYKbJoMhyHchn_cRiL8Y8)

Con respecto a la implementación con listas, se usará una cola para la frontera, lo que permitirá que los elementos menos recientemente añadidos sean los primeros en ser explorados (los menos profundos).

### Prioridad

Se detiene el proceso de búsqueda si se encuentra una solución en vez de considerar todas las opciones.

### Coste uniforme

Se hace la búsqueda, pero no se devuelve la primera encontrada, se establece un orden de exploración basándonos en el coste (se exploran caminos potencialmente más eficientes), devolviendo la óptima.

## Profundidad

Alta velocidad, pero puede llevar a opciones ineficientes.

![](https://lh3.googleusercontent.com/RZvgdMZgk8Ob_J8YEigNAsDKJAMFEZ9O2IFC7WA3yWCB2_4NHm9zuq53GZGOIt2xaWb8nCu7YolpVBToq_gvbqAQdm9TeHwz_uzEYhHVHMuAyY2HC4N93CyN8qA50E7XydKI6B4nQDoVOFAZBkXtalg)

Con respecto a la implementación con listas, se utilizará una pila para la frontera, lo que permitirá que los elementos menos recientemente añadidos sean los primeros en ser explorados (los menos profundos).

### Limitada

Explora en profundidad, rindiéndose cuando el camino supera una profundidad.

### Iterativa

  
  

## Complejidad

![](https://lh4.googleusercontent.com/Dz0r3OQnMAi0_fVmQVXVTk-a6in3Jbi4Wqy7H9-jBCBJiT9CR1auXM-zOnbXkEhSq9aXh18LAafYawU8Stv253X7O0HTxDZjucxlNYBuMczEkWqRjUkIaQf3Co4QsgVhjXh1OPY3LAgimc7DkGnKU0o)

# Búsqueda informada

## Preferente por el mejor

Para establecer los estados más favorables es determinado por la función heurística h(n).

Función heurística: convierte un estado en un valor numérico.

## Tipos de búsqueda

### Avara

La búsqueda avara es la que siempre elige el nodo más prometedor en h(n) sin tener en cuenta el coste.

La frontera será una cola de prioridad atendiendo a h(n).

![](https://lh5.googleusercontent.com/UxCKTPrHA3EdRSVuZncdYBlyed_E_btdTxOx3HRiLyeeyzN_knl2yjWvlHnvE2inK-Y7uE1igR0rCM5t9QnYTn4zR8T23RpXNxLT46L-gC2kR0n86ScWEI0sgKFZE7GnURLJoP7F9LcNYVKFiiVI8nE)

### A*

La búsqueda A* toma en cuenta el h(n) y el coste para tomar las decisiones.

La heurística dará la solución adecuada si se cumple que se subestima el coste real.