# Señales
Una señal es una magnitud física que varia (rango) con  respecto a una variable independiente (dominio). Una señal puede ser representada como una función $f(x)$
## Pulso rectangular
Un pulso de duración T:$$p_1(t) = \begin{dcases}1\ \ \ 0<t<T \\ 0\ \ \ resto\end{dcases}$$
Pulso centrado en T:$$p_1(t) = \begin{dcases}1\ \ \ \frac{-T}{2}<t<\frac{T}{2} \\ 0\ \ \ resto\end{dcases}$$

## Tren de pulsos
Suma de versiones desplazadas de pulsos con amplitud $A_k$$$x(t) = \sum_{K=-N}^N A_K$$
## Impulso unidad
El impulso (delta) es una señal imaginaria que cambia de 0 a 1 en tiempo 0.
Propiedades:
1. $\delta (t)= 0 \ \ cuando \ \ t\neq0$

## Señales senoidales
Las señales senoidales pueden ser representadas por el coseno, siendo definida por tres parámetros:
- Amplitud (positiva)
- Frecuencia (Hz)
- Fase

La representación se realizaría con la siguiente ecuación:$$x(t)=A\cos(2\pi f t + \phi)$$
```ad-summary
title: ejer
$x(t)=-2\cos(4\pi f t + \pi/2)$

Amplitud = 2
frecuencia(
	Hz = 2
	Rad/s = 4pi)
Fase(
	Rad = pi/2
	Grad = 90º)
```

### Fase
La fase es el desplazamiento en el tiempo ( señal senoidal desplazada ), representada por $\phi=-2\pi ft_0 -> \phi = \frac{-2\pi}{T}t_0$

## Señal sinc
$$x(t)=sinc(t)=\frac{sin\ \pi t}{\pi t}$$
En el punto o existe una indeterminación que lleva a :$$sinc(0)=-\lim_{t->0}\frac{\pi \ cos\ \pi t}{\pi}= 1$$
# Potencia e energía
## Potencia instantánea
La potencia instantánea es igual a:$$p(t)=x^2(t)$$
## Energía disipada en un intervalo
Considerando un intervalo $[-\frac{T}{2}, \frac{T}{2}]$ la energía disipada es :$$E^T_x=\int^{\frac{T}{2}}_{-\frac{T}{2}}x^2(t)dt$$
Para calcular la disipación total se da un intervalo infinito: $$E_x=\lim_{T-> \infty}\int^{\frac{T}{2}}_{-\frac{T}{2}}x^2(t)dt=\int^\infty_{-\infty }x^2(t)dt$$
## Potencia media de una señal 
$$P_x=\lim_{T->\infty}\frac{E_x^T}{T}=\lim_{T->\infty}\frac{1}{T}\int^{\frac{T}{2}}_{-\frac{T}{2}}x^2(t)dt $$
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

##  Pulse amplitude modulation (PAM)
$$M=2^b$$
M : número de señales
b: número de bits agrupados
$$S_0(t)=A_0p(t)$$$$S_1(t)=A_1p(t)$$

Cada símbolo es un bit, siendo la velocidad igual a la de bit $v_s=v_b$, y a cada símbolo se le asigna un pulso $v_s=\frac {1}{T}$

```
AB
```


## Atenuación
Perdida de potencia a causa del medio entre el receptor y emisor.
$$G=10\log_{10}\frac{P_y}{P_x}$$
# Respuesta al impulso
# Salida del sistema
A través de la comvolución se puede 
## Propiedades de la comvolución
1. Elemento neutro:  $x(t)*0=0$
2. Elemento unidad:  $x(t)*\delta (t)=x(t)$  $x(t)*\delta (t-t_0)=x(t-t_0)$
3. Conmutativa:  $x(t)*h(t)=h(t) * x(t)$
4. Asociativa:  $(x(t)*h(t))*h_2(t)=x(t)*(h(t)*h_2(t))$
5. Distributiva:  $x(t)*h(t)+x(t)*h_2(t)=x(t)*(h(t)+h_2(t))$

## Convolución de señales  continuas
$$y(t)=\int_{-\infty}^\infty x(\tau)\times h(t-\tau)d\tau$$
