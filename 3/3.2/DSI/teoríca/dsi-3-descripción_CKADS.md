# El modelo del conocimiento
Las tareas intensivas en conocimiento son convertidas en modelos de conocimiento.
## Construcción de los modelos de conocimiento
### Identificación
#### Búsqueda de fuentes
- Factores.
	- Naturaleza de las fuentes.
	- Diversidad de las fuentes.
- Técnicas.
	- Marcar textos con fuentes clave.
	- Entrevistas a expertos.
- Tangible.
	- Listado de fuentes de conocimiento.
	- Resúmenes de textos clave.
	- Glosario de términos.
	- Descripción de los escenarios desarrollados.
- Intangible.
	- El propio entendimiento y comprensión del dominio por parte del ingeniero.

#### Componentes reutilizables
- Dimensión de la tarea.
	- Construcción de una lista de plantillas de tareas.
- Dimensión del dominio.
	- Tipo del dominio.
	- Búsquedas de descripciones estándar.

### Especificación
#### Selección de la plantilla
- Criterio de selección.
	- Naturaleza del sistema.
	- Naturaleza de las entradas y salidas.
	- Restricciones del contexto.

## Plantillas de modelos de conocimiento
- Sistema, elemento sobre el que se aplica la tarea.
- Tareas.
	- Analíticas, solución existente pero no conocida.
		- Clasificación.
		- Diagnóstico.
		- Valoración.
		- Monitorización.
		- Predicción.
	- Sintéticas, solución no existente, se debe crear.
		- Diseño.
		- Configuración de diseño.
		- Asignación.
		- Planificación.
		- Horarios.
		- Modelado.

### Plantillas de tareas
Para establecer una plantilla se debe realizar una caracterización general:
- Object, objeto a calificar.
- Class, grupo de objetos al que pertenece.
- Attribute, característica observable o inferible.
- Feature, par atributo-valor.


## Conocimiento de la tarea

## Conocimiento inferencial
### Inferencias
Las inferencias son pasos de razonamiento menores que componen el problema total.
### Roles de conocimiento
Los roles se dividen en:
- Dinámicos, entrada y salida de la inferencia en tiempo de ejecución.
- Estáticos, especificación de la colección de conocimiento del dominio usada por la inferencia.

### Funciones de transferencia
Codificación de la transferencia de un item de información entre el agente de razonamiento y otro agente del mundo externo.

| Información \\ Iniciativa | Sistema | Externa |
| ------------------------- | ------- | ------- |
| Externa                   | Obtain  | Recive  |
| Interna                   | Present | Provide |

## Conocimiento del dominio
### Esquema de dominio
#### Conceptos
Instancias del dominio que comparten características similares, los conceptos son definidos por atributos, valores que se comparten entre las instancias del dominio.
#### Relaciones
Iteraciones entre conceptos:
- SUBTYPE-OF
- PART-OF
- BINARY_RELATION, se establece un título de la relación.
	- No direccional
	- Direccional
	- Materializada

#### Tipos de reglas
Limitaciones establecidas sobre relaciones entre conceptos.
### Base de conocimiento
La base de conocimiento contiene instancias de los tipos de conocimiento definidos en el esquema del dominio. Para la definición del conocimiento y permitir su reutilización se hacen uso de ontologías, siendo la descripción formal de conceptos y especificación explícita y formal de una conceptualización.
# El modelo de comunicación
El modelo de comunicación específica el intercambio de información entre las tareas llevadas a cabo por diferentes agentes.
## Plan de comunicaciones
Diálogo de alto nivel entre los agentes para realizar una tarea. Las entradas del modelo son:
- TM, listado de las tareas de cada agente con los elementos de información usados.
- KM, conjunto de funciones de transferencia.
- AM, descripción de los agentes.

### Actividades
Para cada agente se selecionan las tareas con intercambio de 
# Caso de estudio