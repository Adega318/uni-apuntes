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
