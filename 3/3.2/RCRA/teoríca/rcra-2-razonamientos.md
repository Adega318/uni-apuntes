# Métodos Categóricos

# Métodos Bayesianos

$\Large P(f)=\frac{N(f)}{N}$
- N un universo.
- f un conjunto de atributos.
- N(f) número de elementos del universo en f.

$\Large P(Dj)=\frac{N(Dj)}{N}$


Expresión generalizada del teorema de Bayes:
$\Large P(A_{0}/E)=\frac{P(E/A_{0})P(A)}{\sum\limits_{i} P(E/A_{i})P(A_{i})}$
P(a1/m1)= (B1+B2+C1+C2)/(N1+N2)

pe dado a = x 
p!e dado a = 1-x

# Cuasi-Estadística
## Factores de certidumbre
### Aspectos básicos
En los modelos cuasi-estadísticos se puede representar cualquier sistema lógico como P(li/Sk)=x.
Esto aplicado a hipótesis nos lleva a que para una dada hipótesis h se tiene una p(h) que al aparecer una evidencia se convierte en p(h/e) siendo p(h/e) > p(h).
Evidencia que respalda la hipótesis:
$MB(h,e)>0$
$MD(h,e)=0$
$MB(h,e)=\frac{p(h/e)-p(h)}{1-p(h)}$

Evidencia que refuta:
$MB(h,e)=0$
$MD(h,e)>0$
$MB(h,e)=\frac{p(h)-p(h/e)}{p(h)}$

Evidencia sin correlación:
$MB(h,e)=0$
$MD(h,e)=0$

Establecemos un factor de incertidumbre $CF(h,e)= MB(h,e)-MD(h,e)$, siendo un valor entre 1 y -1 siendo el 0 la incertidumbre, cabe destacar que la inversa de CF es $CF(h,e)=-CF(\neg h,e)$
Para un conjunto de evidencias E el cálculo del CF(h,E) sería:
$CF(h,E)= \sum\limits^{n}_{i}CFi-\sum\limits^{n}_{i<j}CFi\times CFj + \sum\limits$


### Combinación de evidencias
### Propagación de incertidumbre
## Teoría evidencial
### Fundamentos
### Combinación de evidencias
### Credibilidad, Plausibilidad, Intervalo de Confianza
### Casos particulares
