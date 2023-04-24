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
Pruebas orientadas a comprobar la recuperación del sistema ante fallos, siendo:
- Automática
	- Evaluación
	- Validación
	- Recuperación de datos
	- Reanudación
- Intervenida
## Seguridad
Pruebas orientadas a la vulneración del sistema.
## Esfuerzo
Pruebas de capacidad máxima del sistema para tener consciencia de las limitaciones presentes, teniendo un margen de 20-30% de margen entre máximo y habitual como recomendación.

Métodos comunes de prueba:
1. pruebas de interrupciones.
2. aumento de la tasa de datos en un orden de magnitud.
3. casos de consumo máximo.
4. casos de trashing.
5. casos de búsqueda excesiva de datos.

Una de las variaciones es la prueba de sensibilidad, pruebas para ver los datos que pueden causar picos de procesamiento.
## Despliegue
Prueba de ejecución en  diferentes entornos para asegurar el correcto funcionamiento en los múltiples entornos.
# Depuración
Tras las pruebas comienza la depuración.
1. Síntomas remotos, errores en una parte pueden reflejarse en otra.
2. Síntomas temporales, síntomas que desaparecen temporalmente a causa de la corrección de otro error.
3. Síntomas no causados por errores.
4. Síntomas por error humano.
5. Síntomas por temporización.
6. Condiciones de entrada difíciles de reproducir.
7. Síntomas concluyentes de múltiples errores o procesadores.
## Estrategias
Hay tres acercamientos:
- Fuerza bruta
- Vuelta atrás
- Eliminación de causas
## Corrección
Se debe considerar ante un error su causa del error y donde se puede repetir, posibilidad de la creaciones de errores con la corrección y métodos de prevención de este error.
# Tags
#2- 
#2-2 
#ps 