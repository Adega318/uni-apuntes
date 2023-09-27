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

