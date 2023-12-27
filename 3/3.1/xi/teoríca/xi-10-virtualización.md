La virtualización nace para dar resolución a múltiples problemáticas:
- Almacenamiento.
- Compatibilidad.
- Limitación de recursos a servicios.
# Hiperconvergencia
Esquema para cpds basado en la virtualización que para evitar la caída de la base dea datos se distribuye en múltiples discos en diferentes equipos, virtualizándolos en una cabina de discos virtual. Esto elimina la cabina física aumentando la robustez del sistema y reduciendo el costo (si no fuera por las licencias).
## Sistemas híbridos
Para aumentar la disponibilidad sé hace uso de la hiperconvergencia en paralelo con el uso de una cabina de discos.
# Virtualización
Representación de los recursos hardware en múltiples sistemas, en caso de usar programas específicos para ser virtualizados se hace llamar paravirtualización.
## Beneficios
Los principales beneficios son:
- Consolidación de múltiples equipos hardware.
- Convierte hardware en software (permitiendo modificaciones al hardware real con perturbaciones mínimas).
- Ajustes de configuraciones de manera sencilla.
- Movimiento de máquinas virtuales entre equipos físicos.
## Desventajas
- Fallos físicos con efecto sobre múltiples servicios.
- Fallos de rendimiento se extienden a otros servicios.
- Problemas de gestión de almacenamiento.
## Hypervisors
Sistema que permite la creación y gestión de máquinas virtuales, dividiéndose en dos tipos:
- Tipo 2, aplicación que funciona sobre el sistema operativo.
- Tipo 1, sistema operativo que da directamente el servicio.
## Tecnologías
Las tecnologías de virtualización avarcan server, network, storage y escritorio.
## Guardado de configuraciones
La virtualización permite convertir una máquina en un árbol de ficheros, permitiendo su replicación instantánea y guardado de sesiones sencilla.
# Visualización de servidores
## Hardware en virtualización
El hardware en virtualización, el proceso de coordinación es esencial, siendo definido los recursos otorgados a cada máquina en la configuración de la misma. Con la ram hay problemas, ya que los sistemas operativos no comunican al hardware que memoria está en uso y cuál está libre, para esto se inventaron tres técnicas:
- Páginas libres transparentes, uso de proceso que permite mostrar al hardware las páginas libres para permitir su reclamado.
## Networking
El networking de máquinas virtuales se conectan entre ellas mediante el enrutamiento interno por el hypervisor, 