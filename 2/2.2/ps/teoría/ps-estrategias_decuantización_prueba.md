# Organización
# Pruebas de desarrollo
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
Con la adición de módulos es posible dañar la funcionalidad de los antiguos, la prueba de regresión se basa en reafirmar el funcionamiento de los niveles inferiores, teniendo tres modalidades:
- Muestra, pruebas genéricas del software.
- Adicionales, se enfocan en las funcionalidades afectadas.
- Componentes, se enfocan en las partes del programa que cambiaron.
### Pruebas de humo
Pruebas rápidas basadas en probar las partes claves, enfocándose en:
- Componentes
- Errores paralizantes
## Opciones de estratégicas
### Orientado a objetos
### Aplicaciones web
## Validación
Pruebas de comprobación del correcto funcionamiento, con los siguiente criterios:
- se satisfacen las funcionalidades.
- contenido preciso y adecuado.
Fases de las pruebas con clientes:
- Alfa, pruebas con un grupo reservado de usuarios.
- Beta, pruebas con el publico general.
## Sistema
## Recuperación
Pruevas orientadas a comprovar la recuperación del s
# Tags
#2- 
#2-2 
#ps 