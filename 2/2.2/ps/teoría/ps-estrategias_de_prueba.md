# Organización
# Estrategia
## Unidad
Se establece el componente más pequeño posible y se prueban sus funcionalidades.
![[Pasted image 20230417101612.png]]
Hay que tener en consideración:
-  la descripción de error ininteligible.
- el error indicado no corresponde con el error que se encuentra.
- la condición del error causa la intervención del sistema antes de manejar el error.
- el procesamiento excepción-condición es incorrecto.
- la descripción del error no proporciona suficiente información para  auxiliar en la localización de la causa del error.
## Integración
Tomando los módulos ya probados se crea una estructura de programa.
![[Pasted image 20230420104000.png]]
- Descendente, se comienzan con los niveles superiores y se desciende.
- Ascendente, se comienza por los módulos atómicos y se asciende en complejidad.
### Prueba de regresión
Con la adición de modulos es posible dañar la funcionalidad de los antiguos, 
# Tags
#2- 
#2-2 
#ps 