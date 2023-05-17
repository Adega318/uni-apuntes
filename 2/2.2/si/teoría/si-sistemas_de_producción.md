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
- Base de reglas, reglas que permiten la creación 

## Memoria activa (MA)

![[Pasted image 20230508172143.png]]

Estructura que contiene la información estática del problema:
- datos iniciales
- datos incorporados
- hechos establecidos
- hipótesis de trabajo

Almacena los cambio de estado del sistema, representando nuestro estado actual.
Encargado de aceptar la información externa.
Foco de atracción de las reglas del sistema.
## Motor inferente (MI)
Las funciones del modelo inferente son:
- Examinar la memoria activa y determinar las reglas a ejecutarse, encontrando las conexiones entre inicial y meta.
	- desde la premisa de las conclusiones
	- desde las soluciones a los datos iniciales
	- desde ambos simultáneamente
- Control y organización del proceso de ejecución
- Actualizar memoria activa
- Asegurar autoconocimiento

## Fase de decisión
### Tareas
- Restricción
- Equiparación
- Resolución de conflictos
# Tags
#2- 
#2-2 
#si