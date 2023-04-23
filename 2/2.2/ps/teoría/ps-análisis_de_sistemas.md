# Objetivos
Especificar:
- funciones
- información manejada
- interfaces
- restriciones
# Resultados
El resultado es plasmar los requisitos en modelos dependientes del enfoque seguido cambian.
# Modelos
Razones para el uso de modelos:
- centrarnos en las propiedades importantes
- favorece la comunicación con el usuario
- permite la verificación del análisis

Aporte de los modelos:
- reflejan las necesidades del sistema
- establece la base
- establece un punto de referencia para la validación del sistema.
## Principios
- pocos modelos
- centrarse en el modelo más sencillo
- modelos mutables
- modelos con propósito
- modelos útiles, no perfectos
- centrarse en comunicar, no en ser el maestro de UML
- si no parece correcto, seguramente no lo sea
- obtener feedback
# Análisis estructurado
## Objetivos
- establecer limites del sistema
- modelo logico de procesos
- reflejar las trasformaciones
- simplificar el sistema
- facilitar mantenimien
## Diagrama de flujo de datos (DFD)
**Niveles de aplicación**:
![[Pasted image 20230302104141.png]]
Entre los niveles se debe de cumplir una consistencia de entradas y salidas (Conservación del flujo).
### Diagrama de contexto
El diagrama consta de una única burbuja indicando las estradas y salidas del sistema.
![[Pasted image 20230302104354.png]]
### Diagrama de sistema
En el segundo nivel se determinan los componentes básicos del sistema como burbujas y sus interacciones.
![[Pasted image 20230302104521.png]]
### Niveles posteriores
Los niveles posteriores son usados para concretar las burbujas concretas del nivel anterior.
![[Pasted image 20230302104704.png]]
### Características
- Consistencia entre niveles.
- Inclusión de todos los procesos.
- Inclusión de todos los flujos, siendo los mínimos y necesarios.
- Subsistemas de un solo uso en arranque, eso es parte de otro sistema (migraciones).
- Los DFD no dan temporalidad explícitamente.
- Principio "KIS".
- Todo proceso tiene una salida y entrada.
- Evitar flujos o procesos no etiquetados.
- Evitar almacenes de solo escritura o lectura.
## Diccionario de datos (DD)
Lista organizada que proporciona definición para todos los datos del resto de modelos, evitando la ambigüedad de los mismos. En caso de ser datos elementales se debe definir su composición.
**Datos a definir:**
- Flujos, entidades externas y almacenes (DFD)
- Relaciones, entidades y atributos (E/R)
### Notación
![[Pasted image 20230302111112.png]]
### Metodología
Debemos dar el significado del dato dentro del contexto, composición en caso de tener partes y sus posibles valores en caso de ser un dato elemental.
## Especificación de procesos (EP)
Descripción de entradas, salidas y proceso de transformación de las entradas en las salidas de una burbuja.
## Balanceo entre modelos
Comprobaciones de coherencia entre modelos:
- Los flujos y almacenes del DFD aparecen en el DD.
- Datos del DD aparecen en el DFD.
- Cada burbuja tiene un DFD inferior o EP.
- Los flujos deben coincidir entre EP y DFD.
- Los E/R tienen que ser consistentes con el DFD.
- Las E/R tiene que tener reflejo en DFD.
- Los EP deben crear y eliminar E/R.
## Proceso recomendado
1. Obtener conocimiento
	1. descripción inicial
	2. entrevistar usuarios
	3. refinar
	4. recoger requisitos
2. Modelos de análisis
	1. modelos DFD y E/R
	2. balancear
3. EP
	1. modelos EP
	2. balancear

![[Pasted image 20230306135051.png]]

# Tags
#2- 
#2-2 
#ps