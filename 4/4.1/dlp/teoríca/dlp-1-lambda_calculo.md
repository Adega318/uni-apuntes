# Beta reduction
Proceso de aplicado de una función, donde la primera parte es la función seguida de valor, a esta forma se le llama $\beta-redex$ $(\lambda x.t_1)t_2$.
$(\lambda x.x+1)2 = [x\rightarrow2](x+1)$
# Substitution and free variable capture
Una substitución es definida por:
- $[x\rightarrow s]x=s$
- $[x\rightarrow s]y=y$
- $[x\rightarrow s](\lambda y.t)=(\lambda y.[x\rightarrow s]t)$
- $[x\rightarrow s]t_1 t_2=([x\rightarrow s]t_1)([x\rightarrow s]t_2)$

Al hacer substituciones si se hace una que incluya el nombre de una variable ligada esa variable puede verse capturada, por lo tanto se deve evitar media
