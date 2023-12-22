# Notación
## Números complejos
Los números complejos se representan con la siguiente forma:
$$z = \rho e^{j\theta}$$
### Valores especiales
Los números reales tiene fase 0 : $e^{j\theta}$
# Transformada de Fourier
Para representar de manera directa una señal en el dominio de la frecuencia:
$$X(\omega)=TF\{x(t)\}=\int^{\infty}_{-\infty}x(t)e^{-j\omega t}dt$$
Para obtener $x(t)$ de $X(\omega)$ usaremos la inversa:
$$x(t)=TF^{-1}\{X(\omega)\}=\frac{1}{2\pi}\int^{\infty}_{-\infty}X(\omega)e^{j\omega t}d\omega$$
## Trasformación de señales básicas
### Rectangular
$$x(t) = \begin{dcases}A \quad \frac{-T}{2}<t<\frac{T}{2} \\ 0 \quad resto\end{dcases}$$
$$X(\omega)=2A\frac{\sin(\frac{wT}{2})}{\omega}$$
Al transformarla:
$$X(\omega) = \begin{dcases}1\ \ \ \ -W<\omega<W \\ 0\ \ \ \ \ resto\end{dcases}$$
#### Senoidal
# Relación de Parseval
$$x(t) \rightarrow E_x=\int_{-\infty}^\infty x^2(t)dt =  \frac{1}{2\pi}\int_{-\infty}^\infty |x(\omega)|^2d\omega$$
# Propiedad de linealidad
Al sumar en el dominio del tiempo un numero de señales sumadas a una constante, en el dominio de la frecuencia se suman también.
# Propiedad de escalado en el tiempo
$$x(t)\rightarrow y(t)= x(\alpha t)\alpha = cte$$
