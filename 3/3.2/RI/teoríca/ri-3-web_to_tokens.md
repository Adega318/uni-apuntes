# Web crawler
Pieza de software que recorre la red para obtener páginas web, se basa en partir de una página raid, de la cual obtiene raíces a otras páginas, las cuales son añadidas a las páginas por visitar.
## Estrategias de visita
- Anchura primero, explora el grafo de webs por niveles.
- Profundidad primero, explora por ramas el grafo.
- Focused crawling, prefiere los nuevos enlaces basándose en estrategias predefinidas.

En las estrategias, los focused pueden hacer uso de métricas de prioridad de las páginas:
- In-degree, se puntua por el número de enlaces que llevan a una pagina.
- PageRank, 