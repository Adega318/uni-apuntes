# Web crawler
Pieza de software que recorre la red para obtener páginas web, se basa en partir de una página raid, de la cual obtiene raíces a otras páginas, las cuales son añadidas a las páginas por visitar.
## Estrategias de visita
- Breadth first, explora el grafo de webs por niveles.
- Depth first, explora por ramas el grafo.
- Focused crawling, prefiere los nuevos enlaces basándose en estrategias predefinidas.
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
	- Mantiene únicamente el texto, título y párrafo.
- Automatic wrapper.
- Visual parsing.
	- Parsing basado en el aspecto visual de la página.

## Representación de un documento
Un documento se suele representar por tokens, rompiendo el mismo en palabras, frases y símbolos. Con ciertos idiomas se pueden realizar operaciones extras para tratar sufijos y prefijos y otras peculiaridades de los diferentes idiomas.
Para la tokenización se hace uso de:
- Expresiones regulares (regex)
- Métodos estáticos.

## Tokenización
Proceso de división de un texto en tokens:
- Palabras.
- Frases.
- Símbolos.

La tokenización debe tener en cuenta el lenguaje del texto origen para la reducción de los tokens superfluos. Para realizar la tokenización se suelen usar expresiones regulares o métodos estáticos.
## Indexado de texto
Se puede indexar de múltiples maneras:
- Bolsa de palabras, siendo de gran simplicidad pero perdiendo información sobre su orden.
- N-grams, mejora sobre bolsa de palabras donde se almacenan ciertas combinaciones de palabras como una sola.

### Ley de Zipf
La frecuencia de una palabra en un diccionario es definida por:
$\Large f(k;s,N)=\frac{1/k^{s}}{\sum\limits^{N}_{n=1}(1/n^{s})}$
Donde k es el ranking de la palabra, N el vocabulario y s un parámetro específico del lenguaje.
Esto nos lleva a definir tres tipos de palabras:
- Cabeceras, palabras de poca información repetitivas.
- Colas, mayor cantidad del vocabulario, siendo raras en documentos.
- Normales, palabras de aparición frecuente con información.

### Normalización
Conversión de diversos formatos de palabras en una forma canónica.
### Stremming
Unión de palabras que por reglas morfológicas pueden ser colapsadas en una misma raíz, puede haber problemas en el colapso.