# Metodología
- Definición del proyecto
- Modelo genérico de ciclo
- Metodologías especificas
## Definición de proyecto
Un proyecto se trata de un conjunto de:
- Recursos.
- Organización.
- Productos.
- Objetivos.
- Entorno de riesgo.
Si estos elementos son cotidianos u operaciones estándar de la organización, a estos estándares se les considera operaciones normales y no son proyectos.
## Modelo de ciclo de vida
El modelo de un ciclo de vida:
- Fases propias.
	- Evaluación de riesgos y aprobación del proyecto.
	- Planificación y puesta en marcha.
		- Identificar requisitos de trabajo.
		- Cuantificar requisitos.
		- Identificar requisitos de recursos.
	- Ejecución.
		- Planificación detallada.
		- Organización de la infraestructura.
		- Organización de los recursos.
		- Seguimiento y control.
			- Seguimiento con respecto al plan.
			- Ajustes necesarios.
			- Analizar el impacto.
	- Finalización.
- Fases adyacentes.
	- Gestión de calidad.
	- Gestión de cambios.
	- Gestión de riesgos.
### Recomendaciones
- Planificación disciplinada.
- Seguimiento de estándares.
- Mediciones adecuadas y evaluación de resultados.
- Acciones correctivas adecuadas.
- Liderazgo en los equipos.
# Conceptos

## Tarea/Actividad

Unidad elemental del nivel de planificación, identificada por su duración o consumo de recurso o ambas.
La actividades son independientes y homogéneas.

## Hito

Actividad de duración 0 que indica un momento importante, sirviendo para el seguimiento y control especial. Los hitos se usan también para terceras partes ( subcontratas ).

### Subcontrata

Dos hitos, inicio y fin de subcontrata, unidos por comienzo fin con demora de la duración de la subcontrata. Sobre la subcontrata se debe vigilar:

- Tiempo
- Coste
- Calidad, auditorias para control de calidad.

## Recurso

Un recurso se considera así si:

- Esta sujeto a compartición.
- Origine conflictos de uso.
- Origine coste.

Los recursos podemos clasificaros por:

- Humanos, individuos o grupos homogéneos.
- Materiales, consumibles
- Maquinaria, 

# Técnicas

## Representación

- Diagrama de gantt, representa la duración en el tiempo de las tareas y su relación temporal.
- Red de precedencias, grafo de representación de las dependencias entre tareas del proyecto (grafo dirigido sin ciclos).
  - PDM, hace uso de nodos para representar actividades y las aristas para representar sus dependencias.
  - ADM, los nodos representan inicio y fin de actividades y los vectores el transcurso de la misma.
- Histograma, diagrama que representa el uso de los recursos a trabes del tiempo.

## Estructuración

- WBS, método de división del proyecto en árbol de tareas (se usa para estimar coste y esfuerzo).
- OBS, WBS para recursos.

## Estimación de tiempos

- PERT, estimación de tiempos de actividades de manera probabilista.
  - Tp, estimación pesimista del tiempo.
  - To, estimación optimista del tiempo.
  - Tmp, estimación realista del tiempo.
- CPM, en base a una estimación de tiempos estática y crea el camino critico.

### Camino critico

El camino critico es la serie de tareas que en caso de un retraso se produce el retraso del proyecto al completo.

## Pasos en la planificación

1. Definir actividades
2. Definir restricciones lógicas
   1. CC
   2. CF
   3. FC
   4. FF
   5. Hamaca
3. Asignación de esfuerzo
4. Camino crítico
   1. Holgura, es la cantidad de tiempo que se puede mover sin retrasar el proyecto. (holgura 0 indica que es parte del camino crítico)
5. Optimizar la planificación
   1. nivelación de recursos

# Seguimiento

## Métricas

Las métricas son la medición de los aspectos del proyecto, siendo todo lo no cuantificable incontrolable.

### Tipos

- Producto, cuantifica características del producto.

- Proceso, cuantifica aspectos del proceso de producción.

### Métricas de seguimiento

Se establecen niveles de calidad de planificación de proyecto:

1. Caótico.

2. Repetible, las planificaciones son repetibles.

3. Progreso/esfuerzo/coste, mantenimiento de estas métricas.

#### Métricas de progreso

Medida del progreso del proyecto con respecto a la planificación del proyecto.

#### Métricas de esfuerzo

Medida de las dedicaciones de los recursos a las tareas con respecto a la planificación.
#### Métricas de coste
Tenemos varias métricas para el coste:
- Variación de coste, se calcula como la diferencia entre el coste planificado y real.
- Variación de programa, diferencia entre el coste presupuestado del trabajo realizado y el estimado.
- Coste estimado de finalización, suma del coste del trabajo realizado y estimación de coste restante para la finalización del proyecto

# Arquitectura
Proceso de selección de una herramienta case para la planificación de proyecto.
Dentro del aspecto técnico de los case:
- hardware
	- servidor
	- lan
- software
	- sistema operativo
	- gestor de BDs
	- software gráfico
	- sistema de procesado de texto

Posteriormente se evalúan los aspectos de la herramienta, la decisión se toma con la ponderación de estos valores bajo el criterio de los directivos.
# Entorno organizativo
Documento que estipula la organización y procedimientos, conteniendo:
- Órganos y responsabilidades
- Normas y políticas
- Procedimientos administrativos
- Técnicas y estándares de planificación

# Comunicación
Los cambios en los requisitos y entorno del desarrollo lleva a desviaciones del plan y problemas de plazos, esto tambien puede ser causado por la planificación optimistas.
En consecuencia esto produce el aumento de errores y uso de atajos en el software.
## Negociación
Los desarrolladores somos mallos negociando:
- autismo
- inexperiencia (en nuestro caso)
- desconocimiento de los trucos de negociación

### Negociación conveniente
Método de negociación en la que se buscan conocer los motivos de la otra parte e intentar crear un resultado beneficioso para ambos, evitar comprometerse al acuerdo asta que se aya estudiado la solución.
#### Criterios objetivos
En la negociación se pueden cambiar los criterios por otros criterios objetivos.
## Comunicación eficaz
Comunicación donde se entiende el mensaje que se trata de trasmitir. Dividiendo la comunicación en múltiples canales:
- Verbal
- No verbal
	- contacto visual
	- gestos faciales
	- gesticulación
	- postura y distancia corporal

### Técnicas básicas
- Escucha activa
	- demostrar atención
	- evitar
		- falta de empatía
		- no distraerse
		- no interrumpir
		- no contradecir elementos subjetivos
- Evitar generalización
- Ser breve
- Elegir el lugar para el mensaje a trasmitir

### Comunicación asertiva
Comunicación con las siguientes características:
- Directa
- Honesta
- Respetuosa

Esta comunicación se ve sometida a momentos críticos como los siguientes:
- Compañeros 
	- injustos 
	- no cooperativos
	- expectativas no razonables
	- con opiniones opuestas

Ante estas situaciones la respuesta adecuada se basa en los tipos de comunicación:
- sumisa, causa problemas al no mostrar opiniones pero no causa conflictos.
- agresiva, conducta combativa con gran aporte pero muy conflictiva.
- asertiva, aporta pero no combate.

Entre las anteriores debemos intentar mantener la asertiva mediante técnicas como:
- mensajes yo, centrarse en uno mismo al expresar comportamiento de otra persona para evitar personalizar y crear conflicto.
- disco rayado, reiterar una información para conseguir que el mensaje se comprenda.
- banco de niebla, establecer tu opinión y rechazar la discusión con el interlocutor.
- aplazamiento asertivo, aplazar la discusión para evitar un escalamiento.
- ignorar
- pregunta asertiva
