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
Los códigos binarios son lineales si son cerrados respecto a al suma de n-tuplas.
	$c+c'\in C$
## Código dual y matriz de control de paridad
## Distancia minima

