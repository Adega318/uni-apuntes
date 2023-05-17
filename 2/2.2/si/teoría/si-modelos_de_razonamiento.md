# Modelos y dominios
- Modelos categóricos, modelos que establecen soluciones totalmente verdaderas.
- Modelos probabilísticos, modelo que produce soluciones ciertas con una cierta probabilidad.
- Modelos de razonamiento bajo incertidumbre, modelos con incertidumbre sobre el dominio.
- Modelos de razonamiento en conjuntos difusos, modelos donde los elementos son influidos por matices.

## Modelo categórico
Los problemas los formalizamos con un conjunto X de manifestaciones e Y de interpretaciones.
Problemas lógicos de dada una manifestación caracterizada por una función.
### Proceso sistemático
Partes del proceso con ejemplo:
#### 1. Identificar manifestaciones
Las manifestaciones del ejemplo son M={m(1), m(2)}

![[Pasted image 20230517214206.png]]

#### 2. Identificar las interpretaciones
Las manifestaciones del ejemplo son I={i(1), i(2)}

![[Pasted image 20230517214226.png]]

#### 3. Construir base lógica

![[Pasted image 20230517214643.png]]

#### 4. Construcción de manifestación-interpretación
BLE, posibles combinaciones de M e I :

![[Pasted image 20230517214303.png]]

Para obtener la BLR se aplican las relaciones eliminando los casos superfluos.
Aplicamos R1

![[Pasted image 20230517220913.png]]

Aplicamos R2

![[Pasted image 20230517220939.png]]

Aplicamos R3

![[Pasted image 20230517221000.png]]

Aplicamos R4

![[Pasted image 20230517221023.png]]

BLR = {m1i1, m3i2, m2i3, m4i3, m3i4, m4i4}
## Modelo probabilístico
El modelo probabilístico (bayesiano) se basa en dadas dos posibles acciones (A y B) cual es la probabilidad que ante un resultado E se haya usado A:$$P(A/E)=\frac{P(E/A)P(A)}{P(E)}$$
Tomando las siguientes consideraciones para ejemplificar:

![[Pasted image 20230517222812.png]]

En base a la probabilidad condicional se deduce:$$P(A)P(E/A)=P(E)P(A/E)$$

# Tags
#2- 
#2-2 
#si 