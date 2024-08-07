Sistemas inteligentes basados en reglas frente a una base de hechos.
# Clasificación
## Dirigidos por datos
- Inferencia obtenida cuando los antecedentes de alguna de sus reglas de producción se emparejan al menos una parte de los hechos que describen el estado actual.
- Al ocurrir esto la regla se activa.
- Menos específicos al ejecutar todas las disponibles.

## Dirigidos por los objetos
- Tanto antecedentes como consecuentes de las reglas deben ser considerados como aserciones sobre los datos. En este caso, la activación de las reglas tiene lugar por medio de un encadenamiento regresivo, y el emparejamiento se efectúa a través de las conclusiones de las reglas.
- Para alcanzar una determinada meta hay que configurar un proceso evocativo en el que, de forma recursiva, se van estableciendo los antecedentes de las metas como submetas de orden inferior.
- Son más específicos, porque la ejecución lleva implícito un proceso de búsqueda.

# Arquitectura

![[Pasted image 20230308125411.png]]

## Base de conocimiento
Descripción del dominio en cual el sistema, constituida por:
- Base de hechos, esqueleto declarativo del sistema de producción con la misión de articular los hechos relevantes del dominio.
- Base de reglas, reglas que permiten la creación de los circuitos inferenciales y obtener conclusiones válidas.

![[Pasted image 20230517201432.png]]

## Memoria activa (MA)

![[Pasted image 20230508172143.png]]

Estructura que contiene la información estática del problema:
- datos iniciales
- datos incorporados
- hechos establecidos
- hipótesis de trabajo

Almacena los cambio de estado del sistema, representando nuestro estado actual y aceptar la información externa, siendo el foco de atracción de las reglas del sistema.
## Motor inferente (MI)
Las funciones del modelo inferente son:
- Examinar la memoria activa y determinar las reglas a ejecutarse, encontrando las conexiones entre inicial y meta.
	- desde la premisa de las conclusiones
	- desde las soluciones a los datos iniciales
	- desde ambos simultáneamente
- Control y organización del proceso de ejecución
- Actualizar memoria activa
- Asegurar autoconocimiento

## Ciclos de producción
### Fase de decisión
### Tareas
- Restricción
	- simplifica el proceso de equiparación
	- eliminar reglas superfluas para el estado actual
- Equiparación, identificar y obtener las reglas relevantes para el contexto
- Resolución de conflictos, decisión de las reglas a aplicar con las distintas técnicas:
	- Metarreglas, reglas de categoría superior.
	- Prioridad de reglas, asignar prioridad a reglas de mayor relevancia.
	- Uso de las reglas especificas, tomar las reglas que requieren más información.
	- Regla sobre lo más reciente, aplicar la reglas que usan los datos más recientes.

# Tags
#2- 
#2-2 
#si