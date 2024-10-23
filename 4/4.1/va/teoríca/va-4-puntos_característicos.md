# Bordes
Para la detección de bordes tenemos cuatro características a detectar:
- Normal, vector del cambio en intensidad.
- Dirección, tangente al contorno del borde.
- Intensidad, fuerza del cambio de grises.
- Posición, pixel donde se realiza el cambio en intensidad.
## Primera derivada
Al realizar la primera derivada obtenemos un mapa de vectores de cambio en intensidad, teniendo por cada pixel el cambio en x e y.
### Roberts
Se realiza la primera derivada en lugar de haciendo uso de x e y para la derivada haciendo uso de las diagonales.
### Prewitt
Bordes diagonales, horizontales y verticales.
### Sobel
Bordes con las diferencias horizontales y verticales tomadas en mayor consideración.
### Robinson
Mediante el uso de máscaras se establece la medición de bordes en ocho direcciones.
### Kirsch
Robinson con modificaciones.
## Segunda derivada
La segunda derivada da bordes más concretos, siendo el principal el laplaciano, el cual produce dobles bordes dado lo cual obtenemos bordes donde se produce un cambio de positivo a negativo.
### Laplaciano de gausiano (LoG)
Para tratar la sensibilidad del laplaciano al ruido aplicamos un filtro gausiano integrado en la máscara de la segunda derivada.
### Diferencia de gausianas (DoG)
Para detectar bordes se hace la diferencia de dos gausianas con sigmas ligeramente diferentes, lo
# Esquinas
# Puntos singulares