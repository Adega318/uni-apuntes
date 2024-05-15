# Búsqueda booleana
Query con condiciones booleanas que permite la iteración entre términos, esto lleva a la reducción en tiempo al permitir búsquedas paralelas. Este modelo tiene deficiencias como la imprecisión de las querys y dificultad de formulación.
# Búsqueda por ranking
La recuperación de documentos basándose en su ranking para una dada query permitiendo mayor precisión.
## Modelo de espacio de vectores
Se hacen uso de representación de documentos y querys como vectores de conceptos, siendo la distancia del coseno la relevancia de un dado documento para una query. 
### Pesos
Los pesos permiten determinar la importancia de los términos, los dos principales acercamientos son la frecuencia de término (TF) y frecuencia de documento inversa (IDF).
El tf es calculado como la frecuencia de un término en un documento, este valor es normalizado para reducir la importancia de documentos verbosos, las diferentes normalizaciones son:
- Sublinear, $tf(t,d) = 1+\log(f(t,d))$
- Maximun, $tf(t,d) = \alpha +(1-\alpha)\frac{f(t, d)}{max_{t}f(t,d)}$

El idf se basa en asignar valores altos a términos raros al considerarlos decisivos, calculado como:
 $idf(t)=1+\log(\frac{N}{df(t)})$
 
La combinación de las anteriores da una métrica $w(t,d)=tf(t,d)\times idf(t)$ la cual toma la frecuencia de un término en un documento y en el sistema al completo para determinar la importancia real.
### Similitud
La similitud entre dos vectores puede calcularse mediante múltiples métodos:
- Distancia euclidiana, $dist(q, d)=\sqrt{\sum\limits_{t\in V}[tf(t,q)idf(t)-tf(t,d)idf(t)]^{2}}$
- Similitud de coseno, $cos(V_{q}, V_{d})=V_{q}\times\frac{V_{d}}{|V_{d}|_{2}}$
	- $|V_d|_2$, igual para todos los documentos.

### Ventajas y desventajas
La principales ventajas son:
- Facilidad de implementación

Las principales desventajas son:
- 