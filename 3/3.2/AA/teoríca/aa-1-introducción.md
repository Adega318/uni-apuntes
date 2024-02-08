# Introducción
## Motivación
- Creación de sistemas autoprogramados.
- Introducción de conocimiento mediante ejemplos.
- Solución de problemas sin algoritmos posibles.
- Utilización de la explosión de datos.

## Concepto de aprendizaje
Un sistema se considera capaz de aprender si:
- Interactúa con un entorno o recopila datos del mismo.
- Modifica el comportamiento del sistema o su representación interna.
- Mejora con respecto a algún criterio.

Dentro del aprendizaje en el mundo natural podemos diferenciar:
- Perspectiva conductista.
	- Habituación.
	- Aprendizaje asociativo.
	- Impronta.
	- Imitación.
- Perspectiva filosófica.
	- Conexionismo.
	- Aprendizaje genético.
- Perspectiva humana.
	- Deductivo, obtención de conocimiento mediante información previa y razonamiento.
	- Inductivo, obtención de conocimiento mediante la relación de ejemplos y contraejemplos.
	- Analógico, aplicación de conocimiento presente para situaciones similares.

# Clasificación de tipos de aprendizaje
## Clasificación basándose en la información y resultado
- Aprendizaje supervisado, presentación de ejemplos resuelto.
- Aprendizaje no supervisado, presentación de ejemplos sin resolver.
- Aprendizaje por refuerzo, presentación de ejemplos sin resolver y puntuación de los resultados.

## Clasificación basándose en respuesta deseada
- Aprendizaje de clasificación, la clase a la que pertenece el ejemplo.
- Aprendizaje de regresión, valor numérico continuo.
- Aprendizaje por secuencia, secuencia de valores deseada.

## Clasificación basándose en la interacción entre los datos y el modelo
- Aprendizaje estático, los datos son usados únicamente en el entrenamiento inicial.
- Aprendizaje en línea, los datos son actualizados y el modelo reentrenado de manera continua.
- Aprendizaje pro lotes, reentreno del modelo con lotes de datos de manera periódica.

## Clasificación basándose en la representación del conocimiento
- Aprendizaje simbólico, representación explicita del conocimiento.
- Aprendizaje no simbólico, la información está codificada.
- Aprendizaje mixto.

# Paradigmas
Los diferentes paradigmas más formalizados en el mundo del aprendizaje automático son:
- Supervisado, se establecen etiquetas para las salidas deseadas para cada dato.
- No supervisado, intento de obtener las relaciones entre los datos.
- Por refuerzo, iteración sobre un entorno para la maximización de uno o varios aspectos.
- Semi-supervisado, uso de un set etiquetado y uno sin para reducir el trabajo de etiquetado.
- Basado en esemble, combinación de modelos para aumentar el rendimiento.
- Evolutivo, /////
- Basado en instancias, resolución de problemas basándose en soluciones anteriores a otros problemas.
- Basado en similitud, agrupación de datos basándose en una medida de similitud.
- Profundo, uso de muchas capas para permitir patrones complejos.
- Por transferencia, transferencia de conocimiento entre redes y posterior ajuste.
- Por transferencia profunda, transferencia de información entre redes profundas.
- No supervisado profundo.
- Activo, filtrado de instancias en los datos destacadas.
- Jerárquico, captura de características de forma jerárquica.
- Multi-instancia, aprendizaje sobre grupos clasificados de manera no exhaustiva.
- Refuerzo inverso, ////////
- Basado en conocimiento, /////////
- Incremental, actualización del modelo en función a nuevos datos.
- Probabilístico, uso de métodos probabilístico para representar relaciones.
- Bayesiano, utilización del teorema de bayes
# Aprendizaje inductivo
Adquisición de conocimiento mediante el entorno, teniendo los siguientes conceptos:
- Atributo.
- Instancia.
- Clase.
- Ejemplo.
- Generalización.

Para realizar generalizaciones es de alta importancia la cantidad de datos y diversidad de los mismos, siendo **significativo** y **representativo**.

# Teoremas No Free Lunch