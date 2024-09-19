# Beta reduction
Proceso de aplicado de una función, donde la primera parte es la función seguida de valor, a esta forma se le llama $\beta-redex$ $(\lambda x.t_1)t_2$.
$(\lambda x.x+1)2 = [x\rightarrow2](x+1)$
## Complete Beta-reduction
Las reducciones donde se encuentre una función identidad $(\lambda x.x)$ esta es substituida por id.
$(\lambda x.x)((\lambda x.x)(\lambda z.(\lambda x.x)z))$
$id(id(\lambda z.id\ z))$
$id(id(\lambda z.z))$
$id(\lambda z.z)$
$\lambda z.z$

Para realizar esto tenemos dos principales ordenes:
- Llamada por nombre, en ella esta proivido la redución dentro de abstraci
# Substitution and free variable capture
Una substitución es definida por:
- $[x\rightarrow s]x=s$
- $[x\rightarrow s]y=y$
- $[x\rightarrow s](\lambda y.t)=(\lambda y.[x\rightarrow s]t)$
- $[x\rightarrow s]t_1 t_2=([x\rightarrow s]t_1)([x\rightarrow s]t_2)$

Al hacer substituciones si se hace una que incluya el nombre de una variable ligada esa variable puede verse capturada, por lo tanto, se debe evitar mediante el renombrado de la substitución para que no contenga la variable ligada. Esto se implementa mediante la siguiente norma:
$[x\rightarrow s](\lambda y . t)=(\lambda z . [x\rightarrow s][y\rightarrow z] t)where\ z\notin FV(t)\ and\ z \notin FV(s)$
