# Ejercicios
## ej1
Demuestra que la senoidal $x(t)=A\cos (2\pi ft+\phi)$ es periódica $T=\frac{1}{f}$

// periodica con periodo T si $x'(t+-T)=x'(t)$

$x(t-T)=A\cos(2\pi f(t-T)+\phi)$$=A\cos(2\pi ft-2\pi fT+\phi)=A\cos(2\pi ft-2\pi f\frac{1}{f}+\phi)=A\cos(2\pi ft-2\pi+\phi)=$
$=A\cos(2\pi ft-2\pi+\phi)=A\cos(2\pi ft+\phi)$

// $\cos (x+- 2\pi)=\cos(x)$

## ej3
Señal $x(t)=170\cos (120\pi t-60º)$

// $x(t)=A\cos(wt+\phi)$
//$w=2\pi f$
//$\phi=fase(radianes)$
### a
A= 170
### b
$2\pi f=120\pi -> f=120/2\ Hz$
$w=2\pi f=2\pi 60 = 120\pi \ rad/sec$
### c
$T= 1/f= 1/60 = 0.01666 sec = 16.6 \ ms$
### d
$\phiº = -60$
$\phi^(rad)= \frac{-60\times \pi}{180}=\pi/3 \ rad$
### e
// Desplazamiento en el tiempo es igual a la fase que se produce al desplazar en el //tiempo una de fase 0

$X(t-t_0)=170\cos(2\pi t -60º)=x(t)$
// $\phi = -wt_0$
$t_0 = \frac {\phi^{rad}}{-w}=\frac {-\pi /3}{-120\pi}=1/360 =0.00277\ sec$

### f
Hacer en octave

## ej6
Señales $p(t)$ y $r(t)$ :
$$p(t)= \begin{dcases}A\ \ \ 0<t<T \\ 0\ \ \ resto\end{dcases}$$
$$r(t)= \begin{dcases}A\ \ \ 0<t<3T \\ 0\ \ \ resto\end{dcases}$$
Entre símbolos se debe de dejar un silencio de T segundos.
### a
Envia la letra V (...-) con A = 1

Representación de la señal : 1 0 1 0 1 0 1 1 1
### b
$$v(t)=p(t)+p(t-2T)+p(t-4T)+r(t-6T)$$
### c
L(.-..)

101110101
$$l(t)=p(t)+r(t-2T)+p(t-6T)+p(t-8T)$$
## ej8

### a
...
### b
$u(t) = \begin{dcases}0\ \ \ t<0 \\ 1\ \ \ t>0\end{dcases}$
$p(t)= \begin{dcases}A\ \ \ -T<t<T \\ 0\ \ \ resto\end{dcases}$
$$p(t) =A(u(t+T)-u(t-T)$$
### c
