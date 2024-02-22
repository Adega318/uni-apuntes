Los métodos difusos se basan en el empleo de la ambigüedad en el razonamiento.
# Conjuntos difusos
Un conjunto difuso se representa en función de una función $\mu_A(x)$ de la siguiente manera:
$A \subseteq U / A \mu_A(x)$
Esta función $\mu_A$ se debe de cumplir que sea continúa y coincida en los extremos establecidos. En la zona difusa la función puede tomar muchas formas dependiendo de la realidad a representar.
## Representación de resultados difusos
Para representar los datos obtenidos de una función $\mu_A(x)$ que son continuos de manera lingüística, establecemos intervalos para la asignación de etiquetas lingüísticas, siendo preferiblemente impares para asegurar la existencia de un punto medio y número menor a nueve de manera obligatoria, también se pueden establecer conjuntos complementarios (muy joven = poco viejo).
## Caracterización de conjuntos difusos
Los conjuntos difusos para ser representados se requiere de un referencial (U) y un subconjunto de dicho referencial (A).
$\forall A \subset U:A\_difuso\leftrightarrow$
## Difusos y boole
- Conjunto vacío, $Z\subset U/\exists \mu_{Z} (x) : U\to [0,1]\forall x\in U$
- Identidad,
	- $A\subset U/\exists \mu_{A} (x) : U\to [0,1]\forall x\in U$
	- $B\subset U/\exists \mu_{B} (x) : U\to [0,1]\forall x\in U$
	- $A=B \leftrightarrow \mu_{A}(x)=\mu_{B}(x):\forall x\in U$
- Complementariedad,
- Inclusión,
	- $A\subset U/\exists \mu_{A} (x) : U\to [0,1]\forall x\in U$
	- $B\subset U/\exists \mu_{B} (x) : U\to [0,1]\forall x\in U$
	- $A\subset B \leftrightarrow \mu_{B}(x)\le\mu_{A}(x):\forall x\in U$
- Unión,
- Intersección, 
- Leyes de DeMorgan,
	- 1º,
	- 2º,
- Leyes distributivas,
	- 1º,
	- 2º,
- Producto de conjuntos difusos
	- $A\subset U/\exists \mu_{A} (x) : U\to [0,1]\forall x\in U$
	- $B\subset U/\exists \mu_{B} (x) : U\to [0,1]\forall x\in U$
	- $A\times B \to \mu_{AB}(x)=\mu_{B}(x)\times\mu_{A}(x):\forall x\in U$
	- El producto de dos conjuntos difusos está contenido en la interseción.
- Suma y suma acotada
	- $A\subset U/\exists \mu_{A} (x) : U\to [0,1]\forall x\in U$
	- $B\subset U/\exists \mu_{B} (x) : U\to [0,1]\forall x\in U$
	- $A+ B \to \mu_{A+B}(x)=\mu_{B}(x)+\mu_{A}(x):\forall x\in U$
	- $A\oplus B \to \mu_{A\oplus B}(x)=\mu_{B}(x)\oplus \mu_{A}(x):\forall x\in U$
- Diferencia y diferencia absoluta
- Núcleo de un conjunto difuso
- Relación difusa, establecimiento de un criterio de aproximadamente igual de manera subjeriva.
- Implicación difusa
	- Permisivo
		- $A\subset B/ \exists \mu_{A}(x):U\to [0,1]\forall x \in U$ 
	- Restrictivo
		- $B\subset V/ \exists \mu_{B}(x):V\to [0,1]\forall y \in V$
		- $A\to B\equiv \neg A\oplus B: en\_ U\times V$
- Modus Ponens Generalizado.

## Diferencias entre el razonamiento convencional y difuso
- Modus Ponens Generalizado.
- Certeza.
- Predicados.
- Modificadores.
- Cuantificadores.
- Probabilidades.

## Modos de razonamiento
- Categórico, unión delos descriptores.
- Silogístico, multiplicación de los descriptores.
- Cualitativo, método donde se expresan la representación entre entrada y salida por una colección de reglas difusas.

# Control difuso
El proceso de control difuso se basa en la codificación, base de conocimiento, motor de inferencia y descodificación.
# Métodos formales de representación del conocimiento
- 