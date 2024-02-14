# Ingeniería de conocimiento y SBCs
Las dos principales definiciones son:
- Ingeniería de conocimiento
	- Disciplina para la aproximación sistemática, disciplinada y cuantificable.
- Sistemas basados en conocimiento
	- Sistemas que utilizan conocimiento explícito en un sistema para realizar acciones.

Estos sistemas SBC son caracterizados por:
- Dominio.
- Mantenimiento perfectivo continuo.
- Reutilización de software.
- Justificación y explicación.
- Conocimiento explícito (datos en el propio sistema).

Las ventajas y limitaciones de los sistemas SBC son:
- Ventajas
	- Mantenimiento del conocimiento.
	- Resolución de problemas complejos.
	- Ajuste de objetivos.
	- Tratamiento de la incertidumbre.
	- Explicación del razonamiento.
	- Reducción de costes.
	- Aumento de la fiabilidad.
	- Modularidad.
- Limitaciones
	- Dificultad en la adquisición de conocimiento.
	- Reutilización del conocimiento.
	- Falta de creatividad y sentido común.
	- Obstáculos para el aprendizaje y la adaptación.


# Metodologías adaptadas de la SI
Las principales limitaciones para las metodologías de la SI son:
- Dominio de conocimiento y actividades de adquisición del mismo.
- Dificultad de especificación del conocimiento.
- Dificultad en el establecimiento de requisitos.
- Resultados únicamente visibles al final del desarrollo.
- Generación de explicaciones.
- Mantenimiento complicado.

# Metodologías de modelado de conocimiento
Uno de los procesos más complejos es el modelado del conocimiento para su uso en el sistema, para ello el conocimiento del sistema se representa en un nivel de conocimiento donde es concentrado.
Basándose en lo anterior, la metodología de modelado consiste de:
- Análisis del sistema en el nivel de conocimiento.
- Estructuras de control genéricas, abstractas y reutilizables.
- Análisis y estructuración de tareas generales.

# Metodología CommonKADS
La metodología commonKADS es un estándar basado en el modelado, reutilización y gestión de riesgo. Los productos producidos son comprendidos por la organización, tareas, agentes, conocimiento, comunicación y diseño.

```mermaid
flowchart TD

subgraph "¿Por qué?"
m1[Modelo de organizción]
m2[Modelo de tareas]
m3[Modelo de agentes]
end

subgraph "¿Qué?"
m4[Modelo de conocimiento]
m5[Modelo de comunicación]
end

subgraph "¿Cómo?"
m6[Modelo de diseño]
end

m1 --> m4
m1 --> m5
m2 --> m4
m2 --> m5
m3 --> m4
m3 --> m5

m4 --> m6
m5 --> m6
```
