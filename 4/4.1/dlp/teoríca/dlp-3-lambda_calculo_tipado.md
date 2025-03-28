# Tipos aritméticos
Los principales tipos son Nat y Bool con los siguientes términos:
- true
- false
- if t the t else t
- 0
- succ t
- pred t
- iszero t

Ciertas configuraciones de términos no tienen sentido (succ true) lo que lleva a códigos de error de tipado.
## Tipado
El tipado de términos aritméticos tiene las siguientes reglas:
- T-True, true: Bool
- T-False, false: Bool
- T-Zero, 0: Nat
- T-Succ, $\Large\frac{t_{1}: Nat}{succ\ t_{1}:Nat}$
- T-Pred, $\Large\frac{t_{1}:Nat}{pred\ t_{1}:Nat}$
- T-IsZero, $\Large\frac{t_{1}:Nat}{iszero\ t_{1}Bool}$
- T-If, $\Large\frac{t_{1}:Bool\ t_{2}:T\ t_{3}:T}{if\ t_{1}\ then\ t_{2}\ else\ t_{3}:T}$

Con las reglas anteriores se puede aplicar la derivación de tipos a un término:
$\Large\frac{\frac{\frac{}{0:Nat}(T-Zero)}{iszero\ 0:Bool}(T-IsZero)\frac{}{0:Nat}(T-Zero)\frac{\frac{}{0:Nat}(T-Zero)}{pred\ 0:Nat}(T-Pred)}{if\ iszero\ 0\ then\ 0\ else\ pred\ 0:Nat}(T-If)$

# Tipado simple
Para el tipado de términos lambda se hace uso de la escritura "$T_{1}\to T_{2}$", con esto se añaden los términos:
- $\lambda x:T.t$
- tt
- x

Con esto se crea unas nuevas reglas: 
- T-Abs, $\Large\frac{\Gamma,x:T_{1}|-t_{2}:T_{2}}{\Gamma|-\lambda x:T_{1}.t_{2}:T_{1}\to T_{2}}$
- T-Var, $\Large\frac{x:T\in\Gamma}{\Gamma|-x:T}$
- T-App, $\Large\frac{\Gamma|-t_{1}:T_{11}\to T_{12}\ \Gamma|-t_{2}:T_{11}}{\Gamma|-t_{1}t_{2}:T_{12}}$

En estas normas de tipo se hace uso de un contexto ($\Gamma$) que da el tipo para las variables libres. 
# Extensiones simples
## Tipo unidad
El tipo unidad es un tipo usado para denotar el estado vacío de un término (void en C o Java), esto es denotado por el nuevo tipo $Unit$ y la norma de tipado:
- T-Unit, $\Gamma|- unit:Unit$

## Formas derivadas
### Secuenciado
El secuenciado es una característica útil en los lenguajes permitiendo la evaluación de dos o más términos en secuencia, para añadirlo se implementan las siguientes reglas:
- T-Seq, $\Large\frac{\Gamma|-t_{1}:Unit\ \Gamma|-t_{2}:T_{2}}{\Gamma|-t_{1};t_{2}:T_{2}}$
- E-Seq, $\Large\frac{t_{1}\to t_{1}'}{t_{1};t_{2}\to t_{1}';t_{2}}$
- E-SeqNext, $unit;t_{2}\to t_{2}$

### Comodines
Para expresiones como $\lambda x:T.t$ donde x no es usado en el cuerpo se debería de poder substituir x por un comodín, $\lambda\_:T.t$ 
## Adscripciones
Proceso de asignación directa de un tipo a un término dado, $t\ as\ T$, para la implementación de esta mecánica se requieren:
- T-Ascribe, $\Large\frac{\Gamma|-t_{1}:T}{\Gamma |-t_{1}\ as\ T:T}$
- E-Ascribe, $v_{1}\ as\ T\to v_{1}$
- E-Ascribe1, $\Large\frac{t_{1}\to t_{1}'}{t_{1}\ as\ T\to t_{1}'\ as\ T}$

## Let binding
Permite la asociación de nombres a términos, $let\ x=t\ in\ t$, para la implementación de esta funcionalidad son necesarias las siguientes reglas:
- T-Let, $\Large\frac{\Gamma|-t_{1}:T_{1}\ \Gamma, x:T_{1}|-t_{2}:T_{2}}{\Gamma|-let\ x\ =\ t_{1}\ in\ t_{2}:T_{2}}$
- E-LetV, $let\ x = v_{1}\ in\ t_{2}\to[x\to v_{1}]t_{2}$
- E-Let, $\Large\frac{t_{1}\to t_{1}'}{let\ x = t_{1}\ in\ t_{2}\to let\ x=t_{1}'\ in\ t_{2}}$

## Pares
Método de creación de estructuras de datos complejas con la forma:
- {t, t}
- t.1 (acceso a la posición 1)

Los pares requieren de las siguientes normas:
- T-Pair, $\Large\frac{\Gamma|-t_{1}:T_{1}\ \Gamma|-t_{2}:T_{2}}{\Gamma|-\{t_{1},t_{2}\}:T_{1}\times T_{2}}$
- T-Proj1, $\Large\frac{\Gamma|-t_{1}:T_{11}\times T_{12}}{\Gamma|-t_{1}.1:T_{11}}$
- T-Proj2, $\Large\frac{\Gamma|-t_{1}:T_{11}\times T_{12}}{\Gamma|-t_{1}.2:T_{12}}$
- E-PairBeta1, $\{v_{1},v_{2}\}.1\to v_{1}$
- E-PairBeta2, $\{v_{1},v_{2}\}.2\to v_{2}$
- E-Proj1, $\Large\frac{t_{1}\to t_{1}'}{t_{1}.1\to t_{1}'.1}$
- E-Proj2, $\Large\frac{t_{1}\to t_{1}'}{t_{1}.2\to t_{1}'.2}$
- E-Pair1, $\Large\frac{t_{1}\to t_{1}'}{\{t_{1},t_{2}\}\to\{t_{1}',t_{2}\}}$
- E-Pair2, $\Large\frac{t_{2}\to t_{2}'}{\{v_{1},t_{2}\}\to\{v_{1},t_{2}'\}}$

## Tuplas
Generalización de los pares para n elementos:
- T-Tuple, $\Large\frac{\forall i\ \Gamma|-t_{i}:T_{i}}{\Gamma|-\{t_{i}^{i=1..n}\}:\{T_{i}^{i=1..n}\}}$
- T-Proj, $\Large\frac{\Gamma|-t_{1}:\{T_{i}^{i=1..n}\}}{\Gamma|-t_{1}.j:T_{j}}$
- E-ProjTuple, $\{v_{i}^{i=1..n}\}.j\to v_{i}$
- E-Proj, $\Large\frac{t_{1}\to t_{1}'}{t_{1}.i\to t_{1}'.i}$
- E-Tuple, $\Large\frac{t_{j}\to t_{j}'}{\{v_{i}^{i=1..j-1},t_{j},t_{k}^{k=j+1..n}\}\to\{v_{i}^{i=1..j-1},t_{j}',t_{k}^{k=j+1..n}\}}$

## Registros
Generalización de las tuplas para hacer uso de etiquetas en lugar de posiciones:
- T-Rcd, $\Large\frac{\forall i\ \Gamma|-t_{i}:T_{i}}{\Gamma|-\{l_{i}=t_{i}^{i=1..n}\}:\{l_{i}:T_{i}^{i=1..n}\}}$
- T-Proj, $\Large\frac{\Gamma|-t_{1}:\{l_{i}:T_{i}^{i=1..n}\}}{\Gamma|-t_{1}.l_{j}:T_{j}}$
- E-ProjRcd, $\{l_{i}=v_{i}^{i=1..n}\}.l_{i}\to v_{j}$
- E-Proj, $\Large\frac{t_{1}\to t_{1}'}{t_{1}.l\to t_{1}'.l}$
- E-Tuple, $\Large\frac{t_{j}\to t_{j}'}{\{l_{i}=v_{i}^{i=1..j-1},l_{j}=t_{j},l_{k}=t_{k}^{k=j+1..n}\}\to\{l_{i}=v_{i}^{i=1..j-1},l_{j}=t_{j}',l_{k}=t_{k}^{k=j+1..n}\}}$

## Sumas
...
## Variantes
...
### Opciones
...
###  Enumeraciones
...
### Único campo
...
## Recursión
...
## Listas
...
# Subtipado
El subtipado establece relaciones entre tipos donde en un contexto donde S sea subtipo de T ($S<:T$) permite usar términos de tipo S donde se exija un tipo T.
- T-Sub, $\Large\frac{\Gamma|-t:S\ S<:T}{\Gamma|-t:T}$
- S-Refl, $S<:S$
- S-Trans, $\Large\frac{S<:U\ U<:T}{S<:T}$

## Registros
El subtipado de registros se puede realizar por:
- Anchura, se toma como subtipo el registro que puede contener a su supertipo.
	- S-RcdWidth, $\{l_{i}:T_{i}^{i=1..n+k}\}<:\{l_{i}:T_{i}^{i=1..n}\}$
- Profundidad, los tipos de campos pueden variar siempre y cuando coincidan los campos de los registros.
	- S-RcdDepth, $\Large\frac{\forall i\ S_{i}<:T_{i}}{\{l_{i}:S_{i}^{i=1..n}\}<:\{l_{i}:T_{i}^{i=1..n}\}}$
- Permutación, el orden de los elementos en los registros no afectan al subtipado.
	- S-RcdPerm, $\Large\frac{\{k_{j}:S_{j}^{j=1..n}\}is\ a\ pemutation\ of\{l_{i}:T_{i}^{i=1..n}\}}{\{k_{j}:S_{j}^{j=1..n}\}<:\{l_{i}:T_{i}^{i=1..n}\}}$

## Funciones
Las funciones son afectadas por el subtipado, donde la regla arrow se modifica:
- S-Arrow, $\Large\frac{T_{1}<:S_{1}\ S_{2}<:T_{2}}{S_{1}\to S_{2}<:T_{1}\to T_{2}}$

## Tipo maestro
Cuando trabajamos con subtipado debe de existir un tipo que es contenido en todo otro tipo, este tipo suele ser el conjunto vacío, con reglas:
- S-Top, $S<:Top$
## Casting
### Up-cast
Representación de un tipo como su supertipo, pudiendo realizarse con el uso de una abstracción.
### Down-cast
Asignación de tipos explicita que el typechequer no realiza de manera automática, cast de c, esto se realiza mediante la regla:
- T-Downcast, $\Large\frac{\Gamma|-t_{1}:S}{\Gamma|-t_{1}\ as\ T:T}$
- E-Downcast, $\Large\frac{|-v_{1}:T}{v_{1}\ as\ T\to v_{1}}$

Este tipo de cast pueden ocasionar errores dado que no se realizan demandas sobre la transición.

## Variantes
- T-Varinat, $\Large\frac{\Gamma|-t_{1}:T_{1}}{\Gamma|-<l_{1}=t_{1}><l_{1}:T_{1}>}$
- S-VariantWith, $<l_{i}:T_{i}^{i=1..n}><:<l_{i}:T_{i}^{i=1..n+k}>$
- S-VariantDepth, $\Large\frac{\forall i\ S_{i}<:T_{i}}{<l_{i}:S_{i}^{i=1..n}><:<l_{i}:T_{i}^{i=1..n}>}$
- S-VariantPerm, $\Large\frac{<k_{j}:S_{j}^{j=1..n}>is\ a\ pemutation\ of<l_{i}:T_{i}^{i=1..n}>}{<k_{j}:S_{j}^{j=1..n}><:<l_{i}:T_{i}^{i=1..n}>}$

## Listas
- S-List, $\Large\frac{S<:T}{List\ S<:List\ T}$

## Referencias
Las referencias requieren de subtipado altamente estricto a causa de la lectura y escritura de dichas referencias la cual nos limita.
- S-Ref, $\Large\frac{S<:T\ T<:S}{\mathrm{Re}f\ S<:\mathrm{Re}f\ T}$

### Fuente y sumidero
- T-Deref, $\Large\frac{\Gamma|\Sigma|-t_{1}:Source\ T_{1}}{\Gamma|\Sigma|-!t_{1}:=t_{2}:Unit}$
- T-Assign, $\Large\frac{\Gamma|\Sigma|-t_{1}:Sink\ T_{1}\ \Gamma|\Sigma|-t_{2}:T_{1}}{\Gamma|\Sigma|-!t_{1}:=t_{2}:Unit}$
- S-Source, $\Large\frac{S<:T}{Source\ S<:Source\ T}$
- S-Sink, $\Large\frac{T<:S}{Sink\ S<:Sink\ T}$
- S-RefSource, $Ref\ T<:Source\ T$
- S-RefSink, $Ref\ T<:Sink\ T$