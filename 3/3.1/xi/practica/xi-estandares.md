# tema3
## ej1 (pag15)
Calculo de la tasa de bits y SNR.
### a
$802.11n$, $B = 20MHz$, $S = 3$, $BPSK$, $R = 1/2$, $T_{GI}= 0.8\mu s$
$$V_b = \frac{C}{T_{DFT}+T_{GI}}SR\eta$$
buscamos en la tabla en base al estándar y ancho de banda el número de subportadoras $C=52$ y $T_{DFT} = 3.2\mu s$. Miramos eta con por la modulación BDSK -> $\eta = 1$
$$V_b = \frac{53}{3.2+0.8}3\frac{1}{2}=19.5$$
Miramos en la tabla el SNR, siendo $SNR = 2db$
### b
$802.11ac$, $B = 40MHz$, $S = 2$, $16-QAM$, $R = 3/4$, $T_{GI}= 0.8\mu s$
Miramos en la tabla y calculamos:
$$V_b = \frac{53}{3.2+0.8}3\frac{3}{4}=19.5$$