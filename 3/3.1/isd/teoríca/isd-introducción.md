# Aplicación empresarial ( API )
Una aplicación empresarial abordan necesidades criticas, conectando el backend con el frontend a través de servicios. Los servicios son programas pensados para proporcionar información de una base de datos a aplicaciones ( resolver peticiones ) a través de la red.
Las aplicaciones empresariales deben de cumplir las siguientes características: 
- Escalabilidad, capacidad de crecer en capacidad aumentando los recursos invertidos.
- Alta disponibilidad, resistencia a fallos mediante la duplicación de recursos.
- Transaccionalidad, propiedades ACID ( transacciones unitarias ).
- Seguridad, protección contra ataques y solided de la separación de usuarios.

## Diseño por capas
Método de diseño centrado en la separación del software donde las capas inferiores sirven las peticiones de las superiores a través de una interfaz ( patrón de diseño fachada ), esto lleva al efecto caja negra sobre las capas inferiores. Esta metodología de desarrollo hace sencilla la sustitución y modificación de capas, permitiendo mayor mantenimiento y tolerancia a fallos.
