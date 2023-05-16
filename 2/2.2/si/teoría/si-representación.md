# Agentes basados en conocimiento
Son agentes que constan de una base de conocimiento. Esto hace que su base de conocimiento sea vital para la toma de decisiones.
# Mundo wumpus
Problema de agentes inteligentes con formato de juego.
## Medida de rendimiento
- 1000 salir con oro
- -1000 morir
- -1 por ación
- -10 por flecha

## Entorno
- Tablero de 4x4
- Agente en (1,1)
- Posiciones de los elementos aleatoria
- Probabilidad de cuadrado con fosa 0.2

## Sensores
- Wumpus adyacente (no sabe la casilla)
- Fosa adyacente (no sabe la casilla)
- Oro en su casilla
- Choque al caminar a la pared
- Muerte de un Wumpus

## Actuadores
- Disparar
- Salir por (1,1)
- Coger/Soltar oro de su casilla
- Moverse

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

# Métodos estructurados
## Redes semánticas
Redes de relaciones entre conceptos.
## Frames
Son relaciones con niveles escalonados, un buen ejemplo es el índice de un libro.
### Demons
Los demons son sistemas de actualización y ejecución para los frames.
### Tipos
- Descriptivos, frame centrado en la muestra de datos.
- Control, frame centrado en la especificación de los formatos de datos.

## Reglas de producción
Tenemos tres tipos de reglas:
- if, condición o premisa.
- then, conclusión.
- else, alternativa.

### Tipos
- ifall, todas las cláusulas cumplen.
- ifany, alguna cláusula cumple.
- ifsome, se comprueban todas y luego se hace ifany.

# Tags
#2-
#2-2 
#si