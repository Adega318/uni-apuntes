# Funcionamiento
El sistema detecta la cabecera, apertura de tag, cerradura, texto y comentarios. Al detectar esto se intentarán encajar en el formato correcto de xml, en caso de no coincidir se levantaran errores sintácticos, en caso de coincidir, pero no coincidan los tags se levantara un "tag mismach".
# Consideraciones
1. Se considera unicamente la vesión 1.0 de xml
2. 