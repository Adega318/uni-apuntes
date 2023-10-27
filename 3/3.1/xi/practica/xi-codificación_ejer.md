# pag 42
Código lineal sistemático 4,2
##  A)
distancia mínima sea máxima
(h, k) = (4,2)

| U     | C         |
| ----- | --------- |
| 00    | 0000      |
| 01    | 0101      |
| 10    | 1010      |
| 11    | 1111      | 
| U1 U2 | _ _ U1 U2 |

## B)
determinar la matriz generadora.
$G=[I_k P_{kx(m-k)}]=[I_2 P_{2x2}]$

| 1   | 0   | 1   | 0   | 
| --- | --- | --- | --- |
| 0   | 1   | 0   | 1   |

## C)
Control de paridad
$H=[P_{(m-k)xk}^T I_{m-k}]$

| 1   | 0   | 1   | 0   |
| --- | --- | --- | --- |
| 0   | 1   | 0   | 1   | 

## D)
número de errores detectables y corregibles.
$detectables = dmin-1=2-1=1$
$corregibles = \frac{dmin-1}{2} = 1/2 \rightarrow 0$

# pag 43
k=2 m=5

| u   | c     |
| --- | ----- |
| 00  | 00000 |
| 01  | 01111 |
| 10  | 10100 |
| 11  | 11011 | 

## A)
tasa y si es sistemático
$R=k/m = 2/5$
Es sistemático si las dos primeras posiciones son el mensaje
## B)
generadora

| 1   | 0   | 1   | 0   | 0   |
| --- | --- | --- | --- | --- |
| 0   | 1   | 1   | 1   | 1   | 

## C)
control de paridad y comprueba síndromes

| 1   | 1   | 1   | 0   | 0   |
| --- | --- | --- | --- | --- |
| 0   | 1   | 0   | 1   | 0   |
| 0   | 1   | 0   | 0   | 1   |

$S= V\times H^T$

| 1   | 0   | 0   | 
| --- | --- | --- |
| 1   | 1   | 1   |
| 1   | 0   | 0   |
| 0   | 1   | 0   |
| 0   | 0   | 1   |

S1 = 000
S2 = 000
S3 = 000
S4 = 000

## D)
distancia mínima
$dmin = 2$
## E)
código de hamming con esa misma tasa?
$n=2^m-1$
$K=n-m$

No existe valor de m hamming para nuestra tasa.
## F)
lineal sistemático con tasa 2/5 y dmin 3
$k=2\ m=5$

| u   | c     | p   |
| --- | ----- | --- |
| 00  | 00000 | 0   |
| 01  | 01111 | 4   |
| 10  | 10101 | 3   |
| 11  | 11010 | 3   |

G

| 1   | 0   | 1   | 0   | 1   |
| --- | --- | --- | --- | --- |
| 0   | 1   | 1   | 1   | 1    |

# pag47
## A)
bits en la entrada?
$50\times 64=3200\ bits\ fuente$
## B)
cuantos bits se trasmitimos
n = 3584 bits
## C)
tasa usada
$R=K/m = 3200/3584=0.893$
## D)
tamaño de la matriz control de paridad en ldpc
$H_{(n-k)\times n}$
$n= 2048$
$k=1723$
$325\times 2048$
# pag49
## A)
bits trasmitidos por símbolo QPSK con tasa 3/5
QPSK -> 4 niveles
$bits\ por \ símbolo $
