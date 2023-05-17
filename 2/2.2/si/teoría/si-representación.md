# Agentes basados en conocimiento
Son agentes que constan de una base de conocimiento. Esto hace que su base de conocimiento sea vital para la toma de decisiones.
# Lógica
## Generalidades
- Sintaxis, define sentencias en el lenguaje.
- Semántica, define el significado de las sentencias.
- Implicaciones, relaciones lógicas entre sentencias.

## Implicación
$\alpha\models\beta$, significando que la sentencia $\alpha$ es cierta siempre que $\beta$ es cierta y viceversa.
## Modelos
Los modelos son los posibles estados del entorno, donde se pueden evaluar sentencias. Para una base de conocimiento KB (reglas del mundo + observaciones) los modelos posibles se denotarían como $M(KB)$ y se podrían representar bajo el ejemplo del wumpus como:

![[Pasted image 20230516184433.png]]

## Inferencia lógica
Es el proceso de evaluar sobre los modelos posibles por las percepciones, una sentencia (ver los modelos que salen de una acción). La notación sería:$$Para\ \ M(KB)\subseteq M (\alpha)$$$$Se\ puede\ inferir\ \ KB\vdash_i\alpha$$
Podemos llamar a un algoritmo completo si se puede derivar cualquier sentencia implicada.
### Solidez y completitud
- Solided: i es solido si cuando $KB\vdash_i\alpha$ es también cierto que $KB\models\alpha$
- Completitud: i es completo si cuando $KB\models\alpha$ es también cierto que $KB\vdash_i\alpha$

![[Pasted image 20230516190108.png]]

# Lógica proposicional
Permite definir cualquier cosa para la que existe un procedimiento completo y sólido.
## Sintaxis
- sentencias atómicas de único símbolo de proposición.
- sentencias complejas construidas por las simples y conectivas lógicas.

### Conectivas lógicas

![[Pasted image 20230516192326.png]]

### Formas

![[Pasted image 20230516192413.png]]

## Semántica

![[Pasted image 20230516192523.png]]

### Tablas de verdad para colectivas

![[Pasted image 20230516192608.png]]

## Inferencia
### Enumeración
La inferencia por enumeración es el proceso de emulación de todos los modelos en solida y completa.

![[Pasted image 20230516195000.png]]

Con complejidad $O(2^n)$ para n símbolos.
### Teoremas
- Equivalencia lógica, $\alpha \ y\ \beta$ son equivalentes si son ciertas en el mismo conjunto de modelos.$$\alpha\equiv\beta\iff\alpha\models\beta\ \land\ \beta\models\alpha$$
- Validez, una sentencia es valida cuando se cumple para todos los modelos.
- Satisfacibilidad, una sentencia es satisfacible si es cierta en uno o más modelos.

### Pruebas
- Aplicación de reglas
	- Generación de sentencias a partir de antiguas.
	- Traducción de sentencias en forma normal.
- Comprobación de modelos
	- Enumeración en una tabla de verdad.
	- Mejorar backtracking.
	- Búsqueda heurística en el espacio de modelos.

#### Reglas
- $\alpha\rightarrow\beta , \ \alpha \ entonces\ \beta$
- $\alpha\land\beta ,\ \alpha \ and\ \beta$
- $(\alpha\iff\beta)\rightarrow(\alpha\rightarrow\beta)\land(\beta\rightarrow\alpha)$

##### Búsqueda
La búsqueda de las inferencias se formaliza como:

![[Pasted image 20230516202927.png]]

Se le podrán aplicar los algoritmos de búsqueda (tema 2).
### Monotonicidad
La sentencias inferidas sólo pueden aumentar al añadir información, pudiendo aplicar las inferencias siempre que se tengan las premisas adecuadas.
### Pruebas por resolución

### Factorización

### Forma normal conjuntiva
Toda sentencia se puede expresar como una conjunción de capsulas (forma normal conjuntiva).

![[Pasted image 20230516205744.png]]

#### Convertir a CNF
1. Remplazar "$\alpha\iff\beta$ " con "$(\alpha\rightarrow\beta)\land(\beta\rightarrow\alpha)$"
2. Remplazar "$\alpha\rightarrow\beta$ " con "$\neg\alpha\lor\beta$ "
3. Mover hacia dentro la negación con De Morgan y doble negación
4. Des anidar los operadores "$\land$" y "$\lor$"

### Algoritmo de resolución
- Prueba por refutación, $KB\land\neg\alpha$ es insatisfacible

![[Pasted image 20230516211716.png]]

### Completitud
Si un conjunto de cláusulas es insatisfacible, entonces el cierre de resolución de esas cláusulas contiene la cláusula vacía, comprobado por contraposición.
### Clausula de Definida
Clausulas de disyunción de literales, máximo de 1 positivo.
### KB con cláusulas definidas
1. Las clausulas definidas se pueden escribir como implicación.
	- Premisa, conjunción de literales positivos.
	- Conclusión, único literal positivo.
	- Hecho, sentencia con único literal positivo (sin premisa)
2. inferencia de las clausulas.
	- algoritmo progresivo.
	- algoritmo regresivo.
3. Implicación en tiempo lineal al tamaño de KB.

### Encadenamiento progresivo

![[Pasted image 20230516214637.png]]
![[Pasted image 20230516214652.png]]

### Entrenamiento regresivo

![[Pasted image 20230516214725.png]]

### Backtracking

![[Pasted image 20230516215011.png]]

### Algoritmo de búsqueda local

![[Pasted image 20230516215047.png]]

# Métodos estructurados
Los esquemas no formales de representación del conocimiento verifican las siguientes propiedades:
- Adecuación representacional, el esquema debe de ser capaz de representar las distintas clases de conocimiento del dominio.
- Adecuación inferencial, el esquema elegido debe permitir manipular conocimiento para obtener conocimiento nuevo.
- Eficiencia inferencial, el esquema elegido debe de ser versátil, utilizando información que permita optimizar el proceso inferencial.
- Eficiencia adquisicional, el esquema elegido debe suministrar vías que permitan la incorporación de información y conocimientos nuevos.

## Métodos declarativos
Lo métodos declarativos representan el conocimiento como una colección estática de hechos, que  
solo se pueden manipular con un conjunto genérico y restringido de procedimientos. En otras  
palabras, se dice qué hacer con los datos una única vez, sean del tipo que sean los datos.

Sus ventajas son que aquellos hechos verídicos del dominio se almacenan una sola vez y  
resulta más sencillo aumentar el conocimiento sin modificar el ya existente. Aquí se incluyen  
métodos como las **redes semánticas**, que permiten describir objetos y acontecimientos (hechos)  
al mismo tiempo, o los **marcos (frames)**, que son estructuras que permiten representar desde  
distintos puntos de vista a objetos muy complejos.

### Redes semánticas
Permite describir simultáneamente acontecimientos y objetos, representando el conocimiento como un conjunto de nodos conectados entre sí por medio de arcos etiquetados. Los arcos representan relaciones lingüísticas entre nodos, siendo los 

## Métodos declarativos
Los métodos declarativos representan cada tipo de conocimiento con un procedimiento  
concreto para cada uno, lo cual hace que sea un método bastante dinámico. En otras palabras,  
para cada conocimiento concreto hay que decir qué se hará con él.

Las ventajas son que ponen un mayor énfasis en la capacidad del sistema para inferir nuevo  
conocimiento. Para ello incorporan conocimiento heurístico y manipulan distintos modelos y  
técnicas de razonamiento (por ello son dinámicos) para generar nuevo conocimiento, pero  
siempre basado en un punto de vista de la probabilidad matemática. Aquí se incluyen métodos  
como las **reglas de producción**, que permiten generar conocimiento cuando se cumplen unas  
determinadas condiciones (básicamente es usar IF-THEN-ELSE).
# Tags
#2-
#2-2 
#si