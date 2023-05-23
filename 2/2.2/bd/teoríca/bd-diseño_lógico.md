# Dependencias funcionales
Una dependencia funcional es la restricción entre dos conjuntos de atributos, se denota por $\{X\}\rightarrow\{Y\}$, siendo X e Y dos subconjuntos de atributos de R.
## Reglas
En las reglas de inferencia se ignoran las obvias (sobre uno mismo), considerando solo las imprescindibles.
### Reflexiva
Si tenemos un conjunto contenido en otro, el primero depende del segundo.
X en Y.$$\{X\}\rightarrow\{Y\}$$
### Aumento
Si un atributo determina otro, el segundo des dependiente del primero.$$\{X\}\rightarrow\{Y\}\vDash\{XZ\}\rightarrow\{YZ\}$$
### Transitiva
Si X determina Y e Y determina Z, X determina Z.$$\{\{X\}\rightarrow\{Y\},\{Y\}\rightarrow\{Z\}\}\vDash\{X\}\rightarrow\{Z\}$$
### Descomposición
Si X determina YZ, X determina a Y e Z.$$\{X\}\rightarrow\{YZ\}\vDash\{\{X\}\rightarrow\{Y\},\{X\}\rightarrow\{Z\}\}$$
### Unión
Contraria a descomposición. Bueno para el algoritmo, ya que es mejor que no se repitan las cabeceras.$$\{\{X\}\rightarrow\{Y\},\{X\}\rightarrow\{Z\}\}\vDash\{X\}\rightarrow\{YZ\}$$
### Psudotransitiva
Si X determina Y e WY determina Z, WX determina Z.$$\{\{X\}\rightarrow\{Y\},\{WY\}\rightarrow\{Z\}\}\vDash\{WX\}\rightarrow\{Z\}$$
## Dependencias funcionales
La dependencia funcional $\{X\}\rightarrow\{X\}$ es:
- Trivial si $Y\subseteq X$.
- Elemental si su parte derecha tiene solo un atributo.
- Completa si para todo subconjunto de X se cumple la dependencia.
- Parcial si se puede eliminar un atributo de X sin incumplir la dependencia.

## Cierres
Para calcular un cierre sé presentan las dependencias, se pone el atributo a cerrar en la derecha e izquierda del cierre. Se buscan los atributos de la izquierda del cierre en la derecha de los conjuntos, si se encuentra se añade lo de la derecha del conjunto al cierre y se vuelve a buscar. Si todos los atributos de la relación se encuentran en la izquierda del cierre, la derecha es superclave.
## Equivalencia
Dos conjuntos de dfs E y F son equivalentes si E⁺ = F⁺
# Descomposición
La descomposición es el proceso de atomizar una tabla para cumplir las formas normales.
## Conservación de la dependencia
La conservación de la dependencia es la principal prioridad en la descomposición, aunque no siempre posible.
## Algoritmo
### Ejemplo
R(A,B,C,D)
F = {A->B, B->C}
CC: AD

Dependencias problemáticas:
- A->B impide 2ºFN
- B->C impide 3ºFN
A la hora de descomponer empezamos desde el final, primero las mas altas y si tenemos dos en el mismo nivel se elige la que tenga 

Descomposición:
- Primera vuelta
	R1(B, C)
	F = {B->C}
	CC: B
	
	R2(A, B, D)
	F = {A->B}
	CC: AD
- Segunda vuelta
	R1(B, C)
	F = {B->C}
	CC: B
	
	R2(A, B)
	F = {A->B}
	CC: A
	
	R3(A, D)
	F = {}
	CC: AD
Después de la segunda vuelta todas las relaciones son FNBC.
# Normalización
Estas pruebas evalúan la redundancia a nivel funcional, utilizado en la técnica de diseño [[bd-fases_de_diseño#Ascendente|ascendente]].
Para cumplir una forma se debe de cumplir la anterior.
## 1º FN
El dominio de un atributo debe ser valores atómicos e individuales en un dominio.
## 2º FN
Si todo atributo no primo A en R depende funcionalmente de todas las claves candidatas, don dfs completas.
Es decir, no depende únicamente de una de las candidatas, sino del conjunto de ellas.
## 3º FN
Ningún atributo no primo que dependa transitivamente de una candidata.
## FNBC
Para toda dependencia no trivial, el atributo de la derecha debe de ser clave superclave.
# Desnormalización
A causa de la atomización de las tablas en la normalización se harán joins en el uso, esto puede llevar a una falta de rendimiento, por esto en casos puntuales se puede dejar las tablas en un estado inferior.
# [[bd-diseño_lógico-ejercicios|Ejercicios]]
## Reglas de resolución
1. Agrupar por tipos.
2. Establecer las dependencias provisionales, primero en los tipos y considerando la inversa.
3. Unir las que tengan el mismo lado izquierdo.
4. Establecemos dependencias entre los tipos.
5. Ponemos como claves los que no aparezcan en la derecha.
6. Hacemos las formas normales.
	- Primero resolvemos las más altas.
	- Cogemos las que solo estén en la izquierda.
	- Dividimos en relaciones
# Tags
#2- 
#2-2 
#bd