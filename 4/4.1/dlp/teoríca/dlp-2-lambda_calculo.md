# Beta reduction
Proceso de aplicado de una función, donde la primera parte es la función seguida de valor, a esta forma se le llama $\beta-redex$ $(\lambda x.t_1)t_2$.

$(\lambda x.x+1)2 = [x\rightarrow 2] (x+1)$
## Complete Beta-reduction
Las reducciones donde se encuentre una función identidad $(\lambda x.x)$ esta es substituida por id.
$(\lambda x.x)((\lambda x.x)(\lambda z.(\lambda x.x)z))$
$id(id(\lambda z.id\ z))$
$id(id(\lambda z.z))$
$id(\lambda z.z)$
$\lambda z.z$

Para realizar esto tenemos dos principales órdenes:
- Llamada por nombre, en ella está prohibido la reducción dentro de abstracciones.
- Llamada por valor, se pueden aplicar los redex externos solo cuando el término derecho ha sido reducido a un valor (Usada por la mayoría de lenguajes).
# Substitution and free variable capture
Una substitución es definida por:
- $[x\rightarrow s]x=s$
- $[x\rightarrow s]y=y$
- $[x\rightarrow s](\lambda y.t)=(\lambda y.[x\rightarrow s]t)$
- $[x\rightarrow s]t_1 t_2=([x\rightarrow s]t_1)([x\rightarrow s]t_2)$

Al hacer substituciones si se hace una que incluya el nombre de una variable ligada esa variable puede verse capturada, por lo tanto, se debe evitar mediante el renombrado de la substitución para que no contenga la variable ligada. Esto se implementa mediante la siguiente norma:
$[x\rightarrow s](\lambda y . t)=(\lambda z . [x\rightarrow s][y\rightarrow z] t)where\ z\notin FV(t)\ and\ z \notin FV(s)$


# Sintaxis
## Variables
El cálculo lambda comienza por las variables, donde se encuentran los siguientes elementos:
- termino,$t::= \dots$
- variables, $x$
- abstracciones, $\lambda x.t$
	- binder, $\lambda x.$
	- cuerpo, $t$
- aplicaciones, $t t$
Las variables se pueden considerar enlazadas o libres, una variable se considera enlazada si se encuentra dentro del cuerpo de una abstracción donde el binder contenga dicha variable.
# Semántica operacional
## Reducciones Beta
El proceso de reducción es el medio de computación del cálculo lambda $(\lambda x.t_{1})t_{2}\to[x\implies t_{2}]t_{1}$, siendo la segunda parte el resultado de la substitución de las apariciones enlazadas de $x$ por $t_{2}$ en $t_{1}$, estas reducciones son conocidas como *beta-redex* ($\beta-redex$) y una *forma normal* es la terminología para denotar un término sin reducciones.
## Estrategias de evaluación
- Reducción completa, toda beta puede ser reducida tras una reescritura.
- Orden normal, reduce la reducción más externa.
- **Llamado por nombre**, reducción normal pero sin abstracciones internas.
- **Llamado por valor**, reducción normal, pero donde el argumento es un valor.
# Operaciones semánticas
## Sustitución y variables libres
- $[x\rightarrow s]x=s$
- $[x\rightarrow s]y=y\ if\ y\neq x$
- $[x\rightarrow s](\lambda y.t)=(\lambda y.[x\rightarrow s]t)$
- $[x\rightarrow s]t_1 t_2=([x\rightarrow s]t_1)([x\rightarrow s]t_2)$
Se substitullen las apariciones de variables libres (NO LAS ENLAZADAS).
## Renombrado de variables enlazadas
El renombrado de variables enlazadas es inconsecuente siempre que no se colisione con variables libres en el cuerpo de la abstracción, a esto se le llama $\alpha-conversion$ y permite la sustitución de variables libres sin colisiones con enlazadas.
## Sustitución refinada
- $[x\rightarrow s]x=s$
- $[x\rightarrow s]y=y$
- $[x\rightarrow s](\lambda y.t)=(\lambda y.[x\rightarrow s]t)$
- $[x\rightarrow s]t_1 t_2=([x\rightarrow s]t_1)([x\rightarrow s]t_2)$