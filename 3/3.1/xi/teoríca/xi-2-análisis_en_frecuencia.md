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
$$X(\omega)=2A\frac{\sin(\frac{\omega T}{2})}{\omega}$$
### Sinc
$$x(t)=\frac{\sin{Wt}}{\pi t}$$
$$X(\omega)=\begin{dcases}1\quad -W<\omega<W\\ 0\quad resto\end{dcases}$$
### Coseno
$$\cos(\omega_{0}t)$$
$$\pi\delta(\omega-\omega_0)+\pi\delta(\omega+\omega_0)$$
## Fase de una señal senoidal
Si desplazamos un tiempo $t_{0}$ una onda senoidal obtenemos:
$$x(t-t_{0})=A\cos(\omega t +\phi)$$
$$\phi=-\omega t_{0}=-2\pi \frac{t_{0}}{T_{0}}$$
## Desplazamiento en tiempo
$$x(t-t_{0})\quad \underleftrightarrow{TF\{.\}}\quad X(\omega)e^{-j\omega t_{0}}$$
## Desplazamiento en frecuencia
$$x(t)e^{j\omega_{0}t}\quad \underleftrightarrow{TF\{.\}}\quad X(\omega-\omega_{0})$$
# Relación de Parseval
La energía de una señal real $x(t)$ se puede calcular de la siguiente manera:
$$E_x=\int_{-\infty}^\infty x^2(t)dt =  \frac{1}{2\pi}\int_{-\infty}^\infty |x(\omega)|^2d\omega$$
>[!NOTE] 
>$|X(\omega)|^{2}$ se conoce como la densidad espectral de energía.
# Propiedad de linealidad
Al sumar en el dominio del tiempo un número de señales sumadas a una constante, en el dominio de la frecuencia se suman también.
Para dos señales $x_{1}(t)$ y $x_{2}(t)$ con transformadas $X_{1}(\omega)$ y $X_{2}(\omega)$ respectivamente:
$$a_{1}x_{1}(t)+a_{2}x_{2}(t)\quad\underleftrightarrow{TF\{.\}}\quad a_{1}X_{1}(\omega)+a_{2}X_{2}(\omega)$$
>[!NOTE] Las dos a son constantes cualquieras.
# Propiedad de escalado en el tiempo
El escalado en el tiempo trasforma una señal en otra tal que:
$$x(t)\rightarrow y(t)=x(at)$$
Donde $a$ es un número real positivo.
## TF de escalado en tiempo
La propiedad de escalado en el tiempo de la trasformada de $x(t)$ se define con:
$$x(at)\quad\underleftrightarrow{TF\{.\}}\quad \frac{1}{|a|}X(\frac{\omega}{a})$$
Dando el efecto de:
-  Cuando a > 1 y 1/a <1 la señal se comprime en tiempo, pero expande en frecuencia.
-  Cuando a < 1 y 1/a >1 la señal se expande en tiempo, pero comprime en frecuencia.
# Propiedad de convolución
Para $x(t)$ y $h(t)$ se trasforman:
$$x(t)\times h(t)\quad\underleftrightarrow{TF\{.\}}\quad X(\omega)\times H(\omega)$$
# Propiedad de multiplicación
$$x(t)\cos(\omega_{c}t) \quad\underleftrightarrow{TF\{.\}}\quad \frac{1}{2}(X(\omega+\omega_{c})+X(\omega-\omega_{c}))$$
# Sistema de trasmisión digital
## Modulación
```mermaid
flowchart LR
F[Fuente] --> M[Modulador] --> C[Canal] --Ts--> D[Detector]
```
## Mapeado Gray

## Canales
## Trasmisión
## Probabilidad de error
# Trasmisión de banda base
## Modelo del sistema
## Pulsos
## Comparación
## Ancho de banda mínimo
# Trasmisión paso banda
## Modulación ASK
## Modulación PSK
## Modulación QAM
