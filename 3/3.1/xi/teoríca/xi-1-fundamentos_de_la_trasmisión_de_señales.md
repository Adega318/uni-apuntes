# Señales
Una señal es una magnitud física qué varía (rango) con respecto a una variable independiente (dominio). Una señal puede ser representada como una función $f(x)$.
## Pulso rectangular

Un pulso de duración T:
$$
p_1(t) = \begin{dcases}1\ \ \ 0<t<T \\ 0\ \ \ resto\end{dcases}
$$
Pulso centrado en T:
$$
p_2(t) = \begin{dcases}1\ \ \ \frac{-T}{2}<t<\frac{T}{2} \\ 0\ \ \ resto\end{dcases}
$$
El pulso $p_2$ es la desplazada de $p_1$, cumpliendose la función:$$p_2(t)=p_1(t+\frac{T}{2})$$
## Señal escalón unidad
Señal de altura uno y duración infinita.$$u(t) = \begin{dcases}1\ \ \ t>0 \\ 0\ \ \ resto\end{dcases}$$
Un pulso p puede expresarse en función de u:$$p(t)=u(t)-u(t-T)$$
## Tren de pulsos
Suma de versiones desplazadas de pulsos con amplitud $A_k$
$$x(t) = \sum_{K=-N}^N A_Kp_1(t-kT)$$
## Impulso unidad
El impulso (delta) es una señal imaginaria que cambia de 0 a 1 en tiempo 0.
Con un pulso rectangular de duración $A$ y amplitud $\frac{1}{A}$, si $A$ disminuye, la duración del rectángulo disminuye y su amplitud aumenta (conserva el área, siendo siempre igual a uno), si $A$ es igual a 0 el pulso rectangular se convierte en un pulso unidad.
$$\delta_A(t)=\begin{dcases}\frac{1}{A}\ \ \ 0<t<A \\ 0\ \ \ resto\end{dcases}$$
$$Área=\int^{\infty}_{-\infty}\delta_{A}(t)dt=\int^{A}_0\frac{1}{A}dt=\frac{1}{A}\times A=1$$
### Propiedades
1. $\delta(t)=0\ cuado\ t \neq 0$
2. $\delta(0)\rightarrow \infty$
3. $\int^{\infty}_{-\infty}\delta(t)dt=1$
4. Multiplicación por una constante ( $K\delta(t)$ ), cambia la altura de uno a K.
5. Desplazamiento ( $\delta(t-t_0)$ ) 
## Señales senoidales
La representación de una señal senoidal se realizaría con el coseno en la siguiente ecuación:
$$x(t)=A\cos(2\pi f t + \phi)$$
Pudiendo ser representada alternativamente con la función trigonométrica:
$$x(t)=A\sin(2\pi ft+\varphi)$$
De una onda senoidal se pueden destacar:
- Periodo fundamental, distancia entre máximos (s) $T_0=\frac{1}{f}$
- Frecuencia, número de ciclos por unidad de tiempo (Hz) $f=\frac{1}{T_0}$
- Amplitud, valores entre los que oscila la señal $|A|$
- Frecuencia angular, (rad/seg) $\omega=2\pi f$
	- Permite la simplificación de la representación trigonométrica, $$x(t)=A\cos(\omega t + \phi)$$
	- El periodo fundamental pasa a ser $T_{0}= \frac{2\pi}{\omega}$
### Fase
La fase es el desplazamiento en el tiempo ( señal senoidal desplazada ), representada por $\phi=-\omega t_{0}=-2\pi\frac{t_0}{T_0}$
## Señal sinc
Señal representada por:
$$x(t)=sinc(t)=\frac{sin\ \pi t}{\pi t}$$
En el punto 0 existe una indeterminación que lleva a:
$$sinc(0)=\lim_{t\rightarrow0}\frac{\sin\pi t}{\pi t}= 1$$
# Potencia media y energía
## Potencia instantánea
La potencia instantánea es la cantidad de potencia disipada por una resistencia:
$$p(t)=Ri^{2}(t)=R(\frac{v(t)}{R})^{2}= \frac{v^{2}(t)}{R}$$
## Energía disipada en un intervalo
Considerando un intervalo $[-\frac{T}{2}, \frac{T}{2}]$ la energía disipada en el mismo es:
$$
E^T_x=\int^{\frac{T}{2}}_{-\frac{T}{2}}x^2(t)dt
$$
Si el intervalo es infinito el cálculo de su disipación se convierte en:
$$
E_x=\lim_{T-> \infty}\int^{\frac{T}{2}}_{-\frac{T}{2}}x^2(t)dt=\int^\infty_{-\infty }x^2(t)dt
$$
## Potencia en un intervalo
La potencia de $x(t)$ en el intervalo $[-\frac{T}{2}, \frac{T}{2}]$ es definida por:
$$P_{x}^T=\frac{E_{x}^{T}}{T}=\frac{1}{T}\int^{\frac{T}{2}}_{-\frac{T}{2}}x^{2}(t)dt$$
## Potencia media de una señal
La potencia media de una señal es:
$$
P_x=\lim_{T->\infty}\frac{E_x^T}{T}=\lim_{T->\infty}\frac{1}{T}\int^{\frac{T}{2}}_{-\frac{T}{2}}x^2(t)dt
$$
### Propiedades
- $E_{x}\ge 0 \ y\ P_{x}\ge 0$
- Para una señal con energía infinita la potencia media es 0.
- $0<P_{x}<\infty \Rightarrow E_{x}=\infty$
- Existen señales con energía y potencia media infinita.

```ad-summary
title: ejer1
Energia de una cuadrada de rando $[-\frac{T_0}{2}, \frac{T_0}{2}]$ y amplitud A

$$E_x=\lim_{T-> \infty}\int^{\frac{T_0}{2}}_{-\frac{T_0}{2}}x^2(t)dt=A^2T_0$$

$$P_x = \lim_{T->\infty}\frac{E_x^T}{T}=0$$
```

```ad-summary
title: ejer2
Energia de una triangular de rando $[0, T_0]$ y amplitud A

$$x(t)=  \begin{dcases}\frac{A}{T_0}t_0<t<T_0 \\ 0\end{dcases}$$

$$E_x=\int^{\infty}_{-\infty}\frac{A^2}{T_0^2}t^2dt$$
```

# Modelo de un sistema de comunicaciones digitales
## Pulse amplitude modulation (PAM)
$M=2^b$
M: número de señales
b: número de bits agrupados
$S_i(t)=A_ip(t)$
Las amplitudes se determinan con:
$A_{i}=M-2i-1$
# Distorsión
## Atenuación
Perdida de potencia a causa del medio entre el receptor y emisor.
$G=10\log_{10}\frac{P_y}{P_x}$
# Respuesta al impulso
# Salida del sistema
A través de la convolución se puede 
## Propiedades de la convolución

1. Elemento neutro:  $x(t)*0=0$
2. Elemento unidad:  $x(t)*\delta (t)=x(t)$  $x(t)*\delta (t-t_0)=x(t-t_0)$
3. Conmutativa:  $x(t)*h(t)=h(t) * x(t)$
4. Asociativa:  $(x(t)*h(t))*h_2(t)=x(t)*(h(t)*h_2(t))$
5. Distributiva:  $x(t)*h(t)+x(t)*h_2(t)=x(t)*(h(t)+h_2(t))$

## Convolución de señales  continuas
$S_i(t)=A_ip(t)$ $S_1(t)=A_1p(t)$

Cada símbolo es un bit, siendo la velocidad igual a la de bit $v_s=v_b$, y a cada símbolo se le asigna un pulso $v_s=\frac {1}{T}$
# Distorsión
## Atenuación
Perdida de potencia a causa del medio entre el receptor y emisor.
$G=\frac{P_y}{P_{x}}\ W$
$G_{db}=10\log_{10}(\frac{P_{y}}{P_{x}})=10\log_{10}(P_{y})-10\log_{10}(P_{x})\ db$
## Potencia
| Potencia (dBm) | Potencia (W) | Aplicación                                   |
| -------------- | ------------ | -------------------------------------------- |
| 70             | 10000        | Frecuencia de radio FM                       |
| 60             | 1000         | Máxima salida de radiofrecuencia no regulada |
| 20             | 0.1          | WiFi 2.4GHz                                  |
| 15             | 0.032        | WiFi en dispositivos portátiles              |
El dBm es el decibelio-miliVatio tomando como referencia 1 mW.
$G_{dBm}=10\log_{10}(\frac{P_{y}}{1mW})$
## Retardos
Los retardos cuando son de trasmisión son producidos por los equipos implicados y capacidad de flujo de datos. Los retrasos de propagación son el retraso de la trasmisión por el medio.
## Ruido
Señales de naturaleza aleatoria que modifica la señal transmitida y que puede distorsionar la significativamente.
### AWGN
Ruido que se suma a la señal $x(t)=s(t)+r(t)$, cuando tenemos este tipo de ruido podemos calcular:
- SNR, ratio de señal y ruido (S, potencia de la señal y N, potencia del ruido)
$$SNR(dB)=10\log_{10}(\frac{S}{N})$$
# Multitrayecto
## Salida del sistema
Con la respuesta a un impulso podemos calcular la salida del sistema para cualquier entrada mediante la convolución.
$$y(t)=x(t)\times h(t)=\int^{\infty}_{-\infty}x(\tau)h(t-\tau)d\tau$$
### Propiedades de la convolución
1. Elemento neutro
	- $x(t)\times0=0$
2. Elemento unidad
	- $x(t)\times\delta (t)=x(t)$
	- $x(t)\times\delta (t-t_0)=x(t-t_0)$
3. Conmutativa
	- $x(t)\times h(t)=h(t) \times x(t)$
4. Asociativa
	- $(x(t)\times h(t))\times h_2(t)=x(t)\times(h(t)\times h_2(t))$
5. Distributiva respecto a la suma
	- $x(t)\times h(t)+x(t)\times h_2(t)=x(t)\times (h(t)+h_2(t))$
### Convolución con $\delta(t)$
$y(t)=\int_{-\infty}^\infty x(\tau)\times h(t-\tau)d\tau$

$y(t)=\begin{dcases}0 \qquad t<0 \\ x(t) \quad 0<t<2 \\ 0 \qquad t>2\end{dcases}$

$\delta(t)\times x(t)=x(t)$
### Convolución de dos pulsos rectangulares
Al realizar la convolución de dos pulsos rectangulares se crea un trapecio de salida:
$$y(t)=\begin{dcases}0 \qquad t<0 \\ t \qquad 0<t<1 \\1 \qquad 1<t<2 \\ 3-t \quad 2<t<3\\ 0\qquad 3<t\end{dcases}$$
Para realizar un cálculo gráfico de la convolución tomamos el punto de partida de ambas ondas y los sumamos para obtener el punto de partida de la convolución e igual para el punto de fin, el trapecio crecera desde el punto de inicio la longuitud del pulso menor y descendera esa misma longuitud hasta el filan tras tener un valle.