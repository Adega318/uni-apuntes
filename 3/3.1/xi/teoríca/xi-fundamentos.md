# Señales
Una señal es una magnitud física que varia (rango) con  respecto a una variable independiente (dominio). Una señal puede ser representada como una función $f(x)$
## Pulso rectangular
Un pulso de duración T:$$p_1(t) = \begin{dcases}a \\ b\end{dcases}$$
Pulso centrado en T:

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
$$P_x=\lim_{T->\infty}\frac{E_x^T}{T}=\lim_{T->\infty}\frac{E_x^T}{T} $$