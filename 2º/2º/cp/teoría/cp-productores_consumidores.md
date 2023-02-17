# Descripción
Cuando tenemos productores y consumidores compartiendo un mismo sistema, se debe implementar métodos de sincronización.
# Broadcast
El broadcast se basa en poner a esperar a los threads en un canal y despertarlos simultáneamente al encenderlo. Es una solución simple pero poco eficiente al despertar todos los threads simultáneamente.
# Signals
Las señales se basan en poner a esperar a los threads en un canal, cuando se mande una señal un thread despertará. Es un método ampliamente eficiente pero difícil de implementar.
# Semáforos

^3041e8

Los semáforos se basan en una variable sobre la que dormiremos los threads. Cuando se haga post de esa variable, si el valor es mayor de 0, los threads despertarán.
# Consideraciones
Cuando se pone a esperar a un thread, se debe confirmar la condición despertadora, ya que puede haber variado desde su despertado.