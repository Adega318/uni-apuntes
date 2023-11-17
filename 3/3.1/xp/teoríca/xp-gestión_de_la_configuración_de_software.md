# Introducción
Coordinación del desarrollo de software, reduciendo los errores y facilitando la resolución de los que eventualmente aparezcan. Uno de los principales elementos en este proceso es la trazabilidad del proceso software.
# Objetivos
Facilitar la visibilidad en estado e historia de la versión con la que se trabaja. Esto se consigue con:
- Visibilidad.
	- Estado.
	- Evolución.
- Integridad.
	- Satisfacer las necesidades del usuario.
	- Cumplimiento de requisitos.
	- Trazabilidad desde la concepción al fin.
Las principales actividades para cumplir lo anteriormente mencionado:
- Identificar las configuraciones.
- Control de cambios.
- Gestión de informes de estado.
- Autoría de configuración.
# Conceptos básicos
- La **configuración del software** es la información del conjunto de productos utilizados o generados por el proyecto como resultado del proyecto de ingeniería software.
- **ECS** es un elemento de configuración del software, es la unidad mínima de trabajo del GCS, siendo cada uno de los componentes de la configuración software.
- **Línea base** es la recopilación de ECSs siendo un punto de referencia en el proyecto de desarrollo, los ECS se pueden modificar libremente previamente a ser introducidos en una línea base, obligando a segur un proceso formal de cambios.
# Aspectos relacionados
## Control de versiones
El control de versiones facilita la GCS permitiendo la relación de versiones y recuperación de las mismas.
### Versión
Instancia de un ECS en un momento de desarrollo almacenada en un repositorio con disponibilidad para su recuperación y modificación.
### Revisión
Son lo mismo que versión desde la vista del estándar, en las empresas se le suele considerar cambios menores.
### Modelo de trabajo
```mermaid
flowchart LR
	r[Repositorio]
	l((Versión local))
	r-->|Checkout|l
	l-->|Checkin|r
```
El repositorio almacena las versiones que son solicitadas por el local y modificadas para luego subidas al repositorio. El almacenamiento se realiza normalmente con el almacenamiento completo de unas pocas versiones, con el almacenamiento de los cambios sobre las mismas, siendo a estos llamados el delta y teniendo dos principales:
- Directo, se almacenan los cambios desde la versión inicial.
- Inverso, se almacenan los cambios desde la versión final.
También podemos diferenciar por localización:
- Separados
- Mezclados
### Variantes
Ramificaciones del grafo de modificación base, habiendo tres tipos:
- Temporales, ramificaciones con vida limitada.
- Usar y tirar, variantes de un solo uso (pruebas).
- Permanentes, ramas que continúan de manera separada.
La creación de variantes produce la aparición de configuraciones alternativas, definidas por los ECS y versiones de los mismos. Esto se puede facilitar con la asignación de atributos a los ECSs.
# Release
Las configuraciones entregadas al cliente, debe ser identificada y tener una GCS asociada.
# Ejemplo práctico
Proceso de gestión de configuraciones software:
1. Portada, con firmas de los responsables.
2. Versionado.
3. Distribución.
4. Proceso GCS.
	1. Elementos de configuración.
		1. Documentación.
		2. Software.
	2. Línea base.
		1. LB de requisitos.
		2. LB
	3. Registros de configuración.
	4. Procedimiento de control de cambios.
		1. Registro de solicitudes de cambio.
		2. Análisis de las solicitudes de cambio.
		3. Ejecución de cambios.
		4. Cierre de la solicitud de cambio.
	5. Sistema de gestión de versiones.
		1. Numeración usada.
		2. Entornos de trabajo.

## Procedimiento
En el documento de procedimiento del gcs:
1. **Objeto**, objetivo del procedimiento.
2. **Alcance**, se refiere a los casos donde es aplicable el procedimiento.
3. **Procedimientos relacionados**, procedimientos usados en el procedimiento.
	1. Especificación de requisitos.
	2. Informe de errores.
	3. Atención al cliente.
4. **Aspectos relevantes**, no aplicable a nuestro ámbito.
5. **Aprobaciones**, persona o personas que han aprobado el proyecto (director general).
6. **Responsabilidades**, responsabilidad de los actores en el procedimiento.
7. **Productos de entrada**, materiales de entrada.
	1. ECS
		1. Documenta
8. **Productos de salida**, entregarles de salida.
9. **Mecanismos de control**, personas encargadas de controlar el proyecto.
10. **Base CP**
	1. **Inicio**
	2. **Clasificación**
	3. **Planificación**
	4. **Seguimiento**
		1. cubrir la plantilla de seguimiento
		2. comprobando las hojas de tiempo
		3. reuniéndose con el equipo
		4. gestión de riesgos
		5. ante altos retrasos se replanificará
		6. ante excepciones con alto impacto se documentarán en la plantilla de informe de excepción, enviado al director técnico
	5. **Cierre**
		1. convocación a los implicados a la reunión de cierre
		2. creación del informe de cierre
		3. cierre de las hojas de tiempo
11. **Formularios**
	1. **PP**, plan de proyecto con:
		1. portada
			1. nombre de proyecto y código del mismo
			2. firmas
				1. autor, jefe de proyecto
				2. revisor, responsable de calidad
				3. aprobado, director técnico
			3. fecha
		2. registro de cambios, trazabilidad y autores
		3. índice
		4. introducción, propósito y alcance del plan con nombre, código, objetivo, clasificación, prioridad y dependencias con otros proyectos del proyecto
		5. objetivos del proyecto, lista de entregables con calidades esperadas
		6. organización y responsabilidades, equipo del proyecto con sus roles y responsabilidades
		7. dependencias
		8. gestión de riesgos
		9. desviaciones del sistema de calidad, cambios sobre el sistema de calidad base
		10. seguimiento del proyecto, periodicidad y tipo de seguimiento con los implicados, criterios de replanificación y métricas de seguimiento
		11. cronograma
	2. **InfSeg**
		1. portada
			1. nombre de proyecto y código del mismo
			2. firmas
				1. autor, jefe de proyecto
				3. aprobado, director técnico
			3. periodo de seguimiento
			4. fecha
		2. índice
		3. introducción, visión de la situación del proyecto a fecha del informe
		4. periodo de seguimiento, periodo del informe
		5. tareas realizadas desde el último informe
		6. tareas a realizar
		7. seguimiento de riesgos, hoja de riesgos actualizada
		8. diagrama de Grantt de seguimiento
		9. lista de problemas e incidentes
	3. **InfCierre**
		1. portada
			1. nombre de proyecto y código del mismo
			2. firmas
				1. autor, jefe de proyecto
				2. aprobado, responsable de calidad
			3. fecha
		2. índice
		3. introducción
			1. Resumen
			2. Estado del sistema desarrollado
			3. Revisión de objetivos cumplidos
			4. Dimensión del proyecto
		4. resumen de la gestión
			1. resumen del trabajo realizado (WBS)
			2. errores destacables
			3. conclusiones destacadas
		5. consideraciones principales
			1. Fases del proyecto con su principales consideraciones
			2. documentación
			3. organización del proyecto (OBS)
			4. normas y procedimientos, consideraciones sobre el sistema de calidad y sus desviaciones
			5. tecnicas de desarrollo
			6. esfuerzo, tiempo y coste
	4. **InfExcepción**