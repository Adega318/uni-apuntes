# Interbloqueo
El interbloqueo es cuando dos o más threads esperan por recursos reservados por otros threads que esperan por recursos del primer grupo.
## Condiciones
Las siguientes son las condiciones necesarias para que se produzca un interbloqueo.
- Exclusión mutua, recursos no compartibles.
- Hold and wait, se permite esperar con recursos reservados.
- No apropiación, El sistema operativo no puede forzar la liberación.
- Espera circular, procesos esperando p