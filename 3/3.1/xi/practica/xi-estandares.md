# tema3
## ej1 (pag15)
Calculo de la tasa de bits y SNR.
### a
$802.11n$, $B = 20MHz$, $S = 3$, $BPSK$, $R = 1/2$, $T_{GI}= 0.8\mu s$
$$V_b = \frac{C}{T_{DFT}+T_{GI}}SR\eta$$
buscamos en la tabla en base al estándar y ancho de banda el número de subportadoras $C=52$ y $T_{DFT} = 3.2\mu s$. Miramos eta con por la modulación BDSK -> $\eta = 1$
$$V_b = \frac{53}{3.2+0.8}\cdot3\cdot\frac{1}{2}=19.5$$
Miramos en la tabla el SNR, siendo $SNR = 2db$
### b
$802.11ac$, $B = 40MHz$, $S = 2$, $16-QAM$, $R = 3/4$, $T_{GI}= 0.8\mu s$
Miramos en la tabla y calculamos:
$$V_b = \frac{108}{3.2+0.8}\cdot2\cdot\frac{3}{4}\cdot2=162Mbps$$
Miramos el SNR, siendo $SNR= 18db$
### c
$802.11ax$, $B = 80MHz$, $S = 3$, $256-QAM$, $R = 5/6$, $T_{GI}= 0.8\mu s$
Miramos en la tabla y calculamos:
esta vez no podemos mirar eta, la calculamos $M=256=2^n\rightarrow M=8$
$$V_b = \frac{980}{12.8+0.8}\cdot3\cdot\frac{5}{6}\cdot8=1441Mbps$$
Miramos el SNR, no disponible.
## ej2 (pag15)
$$e=\frac{X}{X_{max}}$$
$$X_{max}= B \frac{simb}{s}$$
$$x=\frac{C}{T_{DFT}+T_{GI}}$$
### a
$802.11n$, $B = 40MHz$, $T_{GI}= 0.4\mu s$
$$e=\frac{X}{X_{max}}= 0.75$$
$$X_{max}= B = 40 M\frac{simb}{s}$$
$$X=\frac{108}{3.2+0.4}$$
### b
$802.11ac$, $B = 40MHz$, $T_{GI}= 0.4\mu s$
$$e=\frac{X}{X_{max}}= 0.75$$
$$X_{max}= B = 40 M\frac{simb}{s}$$
$$X=\frac{108}{3.2+0.4}$$
### c
$802.11ac$, $B = 160MHz$, $T_{GI}= 0.8\mu s$
$$e=\frac{X}{X_{max}}= 0.75$$
$$X_{max}= B = 40 M\frac{simb}{s}$$
$$X=\frac{468}{3.2+0.4}$$