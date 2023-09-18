# Aplicación empresarial
Una aplicación empresarial abordan necesidades criticas, conectando el backend con el frontend a través de servicios. Los servicios son programas pensados para proporcionar información de una base de datos a aplicaciones ( resolver peticiones ) a través de la red.
Las aplicaciones empresariales deben de cumplir las siguientes características: 
- Escalabilidad, capacidad de crecer en capacidad aumentando los recursos invertidos.
- Alta disponibilidad, resistencia a fallos mediante la duplicación de recursos.
- Transaccionalidad, propiedades ACID ( transacciones unitarias ).
- Seguridad, protección contra ataques y solided de la separación de usuarios.

## Diseño por capas
Método de diseño centrado en la separación del software donde las capas inferiores sirven las peticiones de las superiores a través de una interfaz ( patrón de diseño fachada ), esto lleva al efecto caja negra sobre las capas inferiores. Esta metodología de desarrollo hace sencilla la sustitución y modificación de capas, permitiendo mayor mantenimiento y tolerancia a fallos también permitiendo el desarrollo simultaneo de capas una vez establecidas las interfaces.
Las desventajas de las capas son el aumento en la complejidad del software como conjunto pese a la mayor sencillez de las partes y la perdida de eficiencia a causa de la perdida de información entre capas y oportunidades de optimizar.
### Arquitectura de capas
Las arquitectura divide las capas permite la duplicidad de capas concretas sin afectar a las consumidoras y ejecución de distintas capas en maquinas independientes.
#### Capa de interfaz
Otorga interfaz al modelo comunicándose con el directamente o a través de la capa de comunicación.
#### Capa de servicio
Capa para unir la interfaz y modelo cuando están separados por una red.
#### Capa Modelo
Conjunto de lógica de negocio ( lógica de trasformación de datos ) de los casos de uso, implementa todos los casos de uso de forma independiente del frontend ( normalmente ).
Suele dividirse en las siguientes subcapas:
- Capa de acceso a datos, maneja datos de la base de datos y otras fuentes.
- Capa lógica de negocio, implementa la lógica necesaria y usa la capa de acceso a datos para la lectura y escritura.

#### Capa servicios
Permite la interacción de otras aplicaciones con la capa modelo, ofreciendo una API que puede ser invocadas por otras aplicaciones.
#### Capa interfaz gráfica
Permite la interacción entre los usuarios y la capa modelo, ofreciendo una UI y funcionalidades de uso.
### Distribución de capas
#### Servidor de datos
Existe una maquina que gestiona una base de datos central y el resto de maquinas del sistema tienen una interfaz gráfica y modelo. En esta distribución las modificaciones de la capa modelo llevan a actualización de los clientes y compromisos de seguridad a la necesidad de conexión directa con la base de datos y visibilidad del código a la maquina cliente.
#### Servidor de aplicación
Existe un servidor medio con el modelo y los clientes cuentan con la interfaz, tanto el cliente y modelo requieren de una capa de servicio. Este modelo no lleva a la actualización del cliente en caso de modificaciones a la estructura, la seguridad es alta al tener la base se datos conectada únicamente a una maquina.
#### Navegador
Se hace uso de navegador en el lado de cliente y el servidor de Internet web junto con el modelo, esto permite a la aplicación correr en cualquier dispositivo con navegador sin necesidad de actualización en caso de modificaciones.
#### Servidor de recepción
Se basa en el modelo navegador pero separa un 

gnome-terminal --window --full-screen