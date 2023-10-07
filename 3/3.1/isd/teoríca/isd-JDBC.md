# Introducción

La JDBC, jaba data base connectivity es una api que permite la comunicación con bases de datos relacionales. Esto se realiza sobre los drivers java.sql y javax.sql.

## Independencia de la BD

La base de datos debe de ser independiente de la implementación.

# 3 doritos más tarde...

## DataSources

Interfaz usada para manejar la obtención de los datos de acceso a la base de datos, a través de un fichero de configuración.
Esto lleva a problemas como:

- sobrecarga de conexiones, reacción a la falta de conexiones.
- cuello de botella, perdida de rendimiento con la creación y eliminación de conexiones.

Estos problemas se resuelven con la **pool de conexiones**, método que hace uso de una cantidad de conexiones abiertas en arranque, la creación de conexiones es la ocupación del uso de estas conexiones y el cierre su liberación para uso. Esto se realiza con la creación de un objeto que contiene la conexión real e implementa la interfaz conection.
La pool tiene que implementar comprobaciones del estado de las conexiones reales antes de entregarlas, esto se puede hacer mediante el driver o una consulta ligera (ping qwrg).

## Transacciones

Las transacciones se basan en los principios ACID:

- atómico, todas las operaciones se realizan o ninguna.
- consistente, se mantienen la consistencia de la BD.
- aislamiento, las transacciones concurrentes se deben ejecutar como si fueran secuenciales.
- durabilidad, en caso de fallo durante la transacción se mantengan los cambios.

Dentro de la JDBC se pueden realizar consultas en transacción desactivando el commit automático y haciéndolo manualmente al terminar las consultas de la transacción.

### Aislamiento

El aislamiento de las transacciones se divide en niveles, controlado por constantes:

1. serializado, elimina la concurrencia.
2. lecturas repetibles
3. lecturas commited
4. lecturas uncommited
5. nada