1. line = primeros MAX_LINE_LENGTH caracteres del fichero
2. field_break = puntero a ': ' de line
3. sustituimos los ': ' por '\0'
4. field_name = line
5. El hash empieza dos posiciones después del '\0'



sum_file -> crea el hash de l fichero en md5 y lo introduce en md5 con su tamaño.
