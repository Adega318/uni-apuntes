# Principios de diseño
La capa modelo debe ofrecer una api que permita:
- invocar casos de uso
- oculte detalles de implementación

# Método de desarrollo
## Modelado de entidades
Las entidades en el contesto de isd son tablas, con sus campos correspondientes. 
- tiempo, java.math.BigDecimal

## Definición de la API
1. Agrupación de los casos de uso.
   - las agrupaciones deben de ser lógicas.
2. Definición de interfaces para los grupos.
   - un método por caso de uso.
   - las interfaces aplican el método de diseño fachada.

## Gestión de la persistencia
- Dao, herramientas de operaciones básicas.

## Implementación
### Gestión de transacciones
- Casos de uso de solo lectura se establecería auto-commit.
- El resto:
  - Validación de entrada
  - Empezar transacción
  - Comprobar los permisos de la trasacción
    - en caso de no posible commit y excepción.
    - caso correcto commit 
    - error roolback y excepción
