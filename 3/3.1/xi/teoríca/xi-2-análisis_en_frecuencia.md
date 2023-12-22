# Notación
## Números complejos
Los números complejos se representan con la siguiente forma:
$$z = \rho e^{j\theta}$$
### Valores especiales
Los números reales tiene fase 0 : $e^{j\theta}$
# Transformada de Fourier
Toda señal se puede representar como la superposición de cosenos de una cierta frecuencia.
#### Rectangular
$$x(t) = \begin{dcases}A\ \ \ \frac{-T}{2}<t<\frac{T}{2} \\ 0\ \ \ resto\end{dcases}$$
Al transformarla:
$$X(\omega) = \begin{dcases}1\ \ \ \ -W<\omega<W \\ 0\ \ \ \ \ resto\end{dcases}$$
#### Senoidal
# Relación de Parseval
$$x(t) \rightarrow E_x=\int_{-\infty}^\infty x^2(t)dt =  \frac{1}{2\pi}\int_{-\infty}^\infty |x(\omega)|^2d\omega$$
# Propiedad de linealidad
Al sumar en el dominio del tiempo un numero de señales sumadas a una constante, en el dominio de la frecuencia se suman también.
# Propiedad de escalado en el tiempo
$$x(t)\rightarrow y(t)= x(\alpha t)\alpha = cte$$
