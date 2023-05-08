# Sistemas de producción
Sistemas inteligentes basados en reglas frente a una base de hechos.
## Clasificación
### Dirigidos por datos
- Inferencia obtenida cuando los antecedentes de alguna de sus reglas de producción se emparejan al menos una parte de los hechos que describen el estado actual.
- Al ocurrir esto la regla se activa.
- Menos específicos al ejecutar todas las disponibles.

### Dirigidos por los objetos
- Tanto antecedentes como consecuentes de las reglas deben ser considerados como aserciones sobre los datos. En este caso, la activación de las reglas tiene lugar por medio de un encadenamiento regresivo, y el emparejamiento se efectúa a través de las conclusiones de las reglas.
- Para alcanzar una determinada meta hay que configurar un proceso evocativo en el que, de forma recursiva, se van estableciendo los antecedentes de las metas como submetas de orden inferior.
- Son más específicos, porque la ejecución lleva implícito un proceso de búsqueda.

# Arquitectura

![[Pasted image 20230308125411.png]]

## Base de conocimiento
- Base de hechos, esqueleto declarativo del sistema de producción.
- Base de reglas, esqueleto procedimental, permite la contrición de circuitos.
## Memoria activa (MA)

![[Pasted image 20230508172143.png]]

Conocimiento de situaciones detectadas, datos iniciales.
## Motor inferente (MI)
Examina la MA y determina las reglas a ejecutar.
## Fase de decisión
### Tareas
- Restricción
- Equiparación
- Resolución de conflictos
# Tags
#2- 
#2-2 
#si