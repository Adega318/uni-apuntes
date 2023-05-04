# Términos
- [Proceso heurístico](https://en.wikipedia.org/wiki/Heuristic-systematic_model_of_information_processing), proceso donde a causa de la repetición de una tarea, una de las posibles resoluciones obtiene mayor peso que el resto como posible respuesta.
- Programa IA, programas que efectúan comportamiento inteligente

# Planteamientos
## Científico
Intento de reproducir el comportamiento inteligente.
## Ingenieril
Uso de los sistemas para resolver problemas de alta lógica para resolver problemas de dominio estrecho.
# Agentes
## Estructura
### Función
La función es la proyección de una acción basándonos en una percepción. La función se puede representar como una tabla de secuencias de percepción y acción a expresar.
### Programa
El programa es la implementación de la función del agente.
### Arquitectura
La arquitectura es la combinación de estructura de programa, módulos del agente y componentes de interacción.
## Tipos de agente
### Reactivo simple
Agente sencillo que selecciona acciones basándose en su percepción, siendo únicamente reactivo, lo que lleva a una gran dependencia en la percepción.

![[Pasted image 20230217205804.png]]

### Basado en modelos
Agente que hace uso de estados internos, esto le permite interpretar la evolución del mundo y los efectos de sus acciones.

![[Pasted image 20230217205818.png]]

### Basado en metas
Evolución del basado en modelos que expanden sobre la arquitectura, añadiendo metas, lo que le permite planificar las acciones para completar las metas.

![[Pasted image 20230217205832.png]]

### Basado en utilidad
Evolución del basado en metas, expandiendo los sistemas de planificación basándose en el estado actual, añadiendo utilidad a cada estado en función a la meta.

![[Pasted image 20230217205842.png]]

# Tipos de problemas
## Determinismo
Los mundos se pueden caracterizar en deterministas o estocástico, en uno determinista una acción tiene un resultado asegurado, pero uno estocástico el resultado no está asegurado.
## Observabilidad
La observabilidad puede ser completa donde se tienen todos los datos requerirles o parcial donde no todos los datos son accesible o no con la precisión requerida.
# Tags
#2- 
#2-2 
#si