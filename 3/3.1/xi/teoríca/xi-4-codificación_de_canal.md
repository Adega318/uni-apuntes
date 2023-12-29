# Códigos
Un código binario de longitud n y cardinalidad $2^k$ es una colección de $2^{k}$ elementos.
$C(k,n)=\{c^{1},c^{2},...,c^{2^{k}}\},c^{m}$
Los elementos $c^{m}$ son las palabras código, con n como longitud de bloque.
Tasa de codificación: $r=\frac{k}{n}$
# Distancia
- Peso de Hamming de una palabra $w(u)$ es el número de bits distinto de cero que contiene la palabra u.
- Distancia de Hamming entre dos palabras:
	$d(u,v)=d(u-v,0)=w(u-v)$
- Distancia mínima de un código es la distancia mínima entre dos palabras cualquiera.
	$d(C)=min\{d(c,c'):c,c'\in C,c\neq c'\}$
# Decodificación
Usando las distancia de Hamming para una palabra recibida, elegimos la palabra código más próxima.
# Corrección de errores
Un código puede detectar errores siempre y cuando se cumpla $d_{mín}-1$ y pudendo corregir $|\frac{d_{mín}-1}{2}|$
# Códigos lineales
Los códigos binarios son lineales si son cerrados respecto a la suma de n-tuplas.
$c+c'\in C\quad\forall c,c'\in C$
Los códigos lineales tienen las siguientes características:
- Incluye la palabra cero.
- Distancia mínima igual al peso mínimo.
	$d_{min}=min_{v\in C}w(v)$
- Un código binario lineal es un subespacio del espacio vectorial $\{0,1\}^{n}$
## Matriz de control de paridad
H de un código C es la matriz generadora:
$cH^{T}=0$
Por lo tanto, si G es sistemática:
$H=(P^{T}I_{n-k})$
## Distancia mínima
Para cada palabra código de peso $p_H$ existen $p_H$ columnas de H cuya suma es el vector 0. De igual modo, si existen $p_H$ columnas de H que suman 0, entonces existe una palabra código con peso de Hamming $p_H$.
Este teorema se interpreta como que la distancia mínima de un código es igual al mínimo número de columnas de H que hay que sumar para obtener 0.
## Detección de errores
Si el síndrome de una palabra recibida es distinto de 0, es seguro que se ha producido un error.
$s'=c'H^{T}$
## Códigos Hamming
Los códigos con $d_{min}=3$ para cualquier longitud de bloque n, puede corregir errores de 1 bit.
Matriz de control de paridad $H_{m\times(2^{m}-1)}$ formada por las posibles m-tuplas no nulas.
## Decodificación óptima mediante el síndrome
Al trasmitir por una canal un mensaje c se produce un error e y recibimos $c'=(c+e)$
- Síndrome: $s'=eH^{T}$
- Standard array, tabla que a cada síndrome le hace corresponder el patrón de error con menos peso que lo produce.
- Decodificación óptima mediante síndrome.
	- Cálculo del síndrome de la palabra recibida $s'=c'H^{T}$.
- La regla de decodificación es óptima, ya que la probabilidad de un patrón de error es mayor que la de cualquier otro con mayor peso.
## Probabilidad de error $p_{we}$
- Código con $d_{mín}$ corrige todos los patrones de hasta $t=[\frac{d_{mín}-1}{2}]$ errores.
- 