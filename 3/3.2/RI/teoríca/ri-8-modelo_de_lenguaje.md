Los modelos de lenguaje establecen probabilidades de secuencias de palabras, para lo cual existen múltiples modelos.
# Modelos
## Unigram
Se consideran las palabras con probabilidades independientes.
$p(w_{1}...w_{n})= p(w_{1})...p(w_{n})$
$s.t.{p(w_{i})}_{i=1}^{N}, \sum\limits_{i}p(w_{i})=1, p(w_{i})\ge 0$
Esta es una de las opciones y populares por su simplicidad.
## Modelos avanzados
- N-gram, usa la probabilidad condicionada de n-1 palabras.
- Remote-dependence.
- Structured.

# Recuperación por estimación
Proceso de puntuación por la probabilidad de la query.
$\log(p(q|d))=\sum\limits_{i}\log(p(q_{i}|d))$
El acercamiento más común es la **máxima probabilidad estimada** (MLE)
$P_{ML}(w)=\frac{count\ of\ w}{count\ of\ all\ words}$
Teniendo el problema de la perdida de los sinónimos y relaciones sintácticas, para evitar esto se hace uso de técnicas de smoothing.
## Smoothing
La idea general es reducir la probabilidad de palabras muy habituales y redistribuirlas en las menos ocurrentes. 
- Additive, aplica un suavizado general.
$\large p(w|d)=\frac{c(w,d)+1}{|d|+|V|}$
- Referencia, en caso de no estar en el documento, dar el valor de la probabilidad en REF, documento de referencia.
$\large\alpha_d=\frac{1-\sum_{w\in d}p(w|d)}{\sum_{v\notin d}p(w|REF)}$
$\large p(w|d)=\alpha_dp(w|REF)$
- Descuento absoluto, reduce una cantidad constante de todos los terminos.
$\large p(w|d)=\frac{max(c(w,d)-\delta , 0)+\delta |d|_u p(w|REF)}{|d|}$
- Jelinek-Mercer, usa un parámetro lambda para ponderar la importancia de la colección y el documento.
$\large p(w|d)=(1-\lambda)\frac{c(w,d)}{|d|}+\lambda p(w|REF)$
- Dirichlet.
$\large p(w|d)=\frac{c(w,d)+\mu\frac{c(w,C)}{|C|}}{|d|+\mu}$