Un ciclo de vida es la adquisición, suministro, desarrollo y mantenimiento del software. Los ciclos de vida son ampliamente dependientes del proyecto y organización.
En el siclo de vida se deben de determinar las fases del proceso software y sus ciclos de transición.
Ciclo de vida y ciclo de vida de desarrollo: Estos dos términos son parecidos, pero tienen un matiz, siendo el ciclo de vida, el tiempo de vida y desarrollo y el mantenimiento.
# Modelos de codificación
## Directa
Es el proceso de creación de código y corrección de errores simultáneamente, es un modelo artesanal y válido únicamente para pequeños proyectos.
## Cascada
Modelo basado en la realización secuencial de las siguientes fases:
- Requisitos
- Análisis
- Diseño
- Programación
- Pruebas
- Implantación
- Mantenimiento

Este acercamiento tiene las siguientes ventajas:
- Se establece un marco de referencia para el desarrollo.
- Fácil coordinación de recursos.
- Fácil establecimiento de hitos, control del progreso de desarrollo y detección de desviaciones.

Desventajas:
- Necesidad de establecer todos los requisitos en las fases iniciales.
- Gran rigidez del desarrollo.
- Dificultad de detección de problemas.
- No hay productos intermedios.

## En V

![[Pasted image 20230429194926.png]]

Es un modelo basado en que las fases producen salidas para más de una de las siguientes fases, usualmente planes para las posteriores, siendo una variante del modelo de cascada.
Esto formará dos ramas, una descendente con el diseño y una ascendente con el desarrollo con movimientos laterales de la de diseño a desarrollo (planes de pruebas).
Ventajas:
- Hereda las ventajas del de cascada.
- Favorece la consideración de las pruebas.

Desventajas:
- Comparte la desventaja del cascada de establecer todos los requisitos al comienzo.
- Gran rigidez, aunque más que cascada.
- No hay parciales.
## Prototipado
Es un modelo basado en la recolección de información, prototipado basándose en la información con feedback del cliente para la modificación del mismo, esto es usado en casos de clientes sin requerimientos claros.
Podemos dividir los prototipos en dos familias, desechables, con la intención de ser un vehículo para la obtención de información, y evolutivos, pensados para ser mejorados en el producto final.
Ventajas:
- Gran flexibilidad.
- Producción de productos intermedio.

Desventajas:
- Posibles confusiones con los clientes con el estado del producto.
- Necesidad de toma de decisiones de desarrollo tempranas con posible necesidad de cambio.
# Modelos evolutivos
Modelos basados en la creación de pasos intermedios funcionales.
## Incremento

![[Pasted image 20230429202250.png]]

## Incremental

![[Pasted image 20230429202315.png]]

El modelo incremental se basa en la ampliación y mejora de las funcionalidades del producto en consecuentes versiones, cada versión es un producto funcional, pudiendo usar otros modelos para el desarrollos de las versiones.
Ventajas:
- Mantiene el desarrollo cercano a la necesidad del cliente.
- Mayor flexibilidad.
- Progreso de calidad y estabilidad con interacciones.

Desventajas:
- Complejidad de la definición del núcleo del programa.
- Complejidad de la priorización de funcionalidades.
- Validez temporal de las funcionalidades.
## Espiral

![[Pasted image 20230429202922.png]]

Aplicable en proyectos de alto riesgo. El procedimiento son iteraciones consecutivas de un modelo inicial, dividiendo el desarrollo en cuatro sectores distintivos:
1. Determinación, primer paso, donde se establecen requisitos y planificación del proyecto.
2. Evaluación, se evalúan planes alternativos e intentan solventar los riesgos.
3. Desarrollo
4. Revisión, se revisa y evalúa el proyecto preparando el siguiente ciclo de espiral.

Ventajas:
- Permite adaptarse a entornos cambiantes.
- Gestión de riesgos.

Desventajas:
- Requerimientos de personal con alta competencia en consideración de riesgos.
## Características
- Desarrollo iterativo e incremental
- Eliminación de fronteras entre fases
- Incorporan bibliotecas de clases y otros componentes reutilizables

![[Pasted image 20230218174434.png]]

# Tags
#2- 
#2-2 
#ps 