Maven en un proyecto se encarga de:
- Estructura estándar de proyecto.
- Configuración en xml.
- Gestión de dependencias.
- Construcción de proyecto.

Esto trae varias ventajas:
- Mejora de la calidad del producto.
- Acelerar la compilación.
- Minimizar compilaciones erróneas.
- Mejor trazabilidad.

# Configuración
La configuración de maven se define en un fichero pom.xml, encontrándose siempre en la raíz del proyecto.
# Ciclo de vida
Maven tiene multiples fases de ciclo de vida que realiza secuencialmente, las principales son:
- Compilación.
- Test.
- Package.
- Install.
- Deploy.

Estas fases tienen unas metas definidas por las extensiones que en caso de que uno no se complete no se pasa a la siguiente fase del ciclo de vida.