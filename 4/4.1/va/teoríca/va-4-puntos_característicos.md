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
# Esquinas
# Puntos singulares