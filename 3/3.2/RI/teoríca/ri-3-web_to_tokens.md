# Web crawler
Pieza de software que recorre la red para obtener páginas web, se basa en partir de una página raid, de la cual obtiene raíces a otras páginas, las cuales son añadidas a las páginas por visitar.
## Estrategias de visita
- Anchura primero, explora el grafo de webs por niveles.
- Profundidad primero, explora por ramas el grafo.
- Focused crawling, prefiere los nuevos enlaces basándose en estrategias predefinidas.

En las estrategias, los focused pueden hacer uso de métricas de prioridad de las páginas:
- In-degree, se puntúa por el número de enlaces que llevan a una página.
- PageRank, una página obtiene puntuación por sus contenidos.
- Topical relevance, únicamente visita páginas asociadas al tema, definiendo su asociación con similitud en el ancla.

## Evasión de duplicados
Para evitar duplicados se debe comprobar que las nuevas páginas encontradas no sean páginas ya visitadas con diferente url, esto se puede solucionar con la comparación de hash de la nueva página con el de las ya visitadas.
## Política de educación
La política de educación se basa en que el crawler siga unas normas establecidas por la web con amenaza de desconexión.
# Técnicas de análisis de texto
## Html parsing
- Shallow parsing.
	- Elimina los tags.
	- Mantiene únicamente el texto título y párrafo.
- Automatic wrapper
- Visual parsing

## Representación de un documento
Un documento se suele representar por tokens, rompiendo el mismo en palabras, frases y símbolos.
