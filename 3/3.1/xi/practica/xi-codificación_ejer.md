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
$$