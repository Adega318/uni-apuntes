# Generales
- % -> comentario
- help 'comando' -> info sobre el comando
- x = 'algo' -> variable

# Vectores
- z = 'x':'y' -> vector con los valores de x a y
- z = 'x':'z':'y' -> vector de x a y elementos contados de z en z
- z('posiciones') -> extraer valores
- z('posiciones') = 'valores' -> darle valor a una posición
- z + z2 -> suma
- z - z2 -> resta
- z .* z2 -> producto elemento a elemento
- (z)' * z2 -> producto interno
- z ./ z2 -> división elemento a elemento
- z .^ z2 -> exponente elemento a elemento

# Matrices
- z = zeros('x', 'y') -> matriz de 0 de tamaño x * y
- z('x', 'y') -> extraer de la posición
- z('x', 'y') = 'valor' -> asignar valor a la posición
- z + z2 -> suma
- z - z2 -> resta
- z * z2 -> producto 
- z .* z2 -> producto elemento a elemento
- z ./ z2 -> división elemento a elemento
- z .^ z2 -> exponente elemento a elemento

# Lógica
- & -> and
- | -> or
- ~ -> negación
- < -> menor
- > -> mayor
- == -> igual
- >= -> mayor igual
- <= -> menor igual
- ~= -> distinto
- for i = 'valor inicial':'paso':'valor final'; 'comandos'; end; -> bucle for

# Gráficos
- figure ('num') -> crea una figura con el número dado (número opcional), en caso de ya existir y no estar activa la activa.
- subplot('num_filas', 'num_columnas', 'posición') -> subdivide una figura, la posición indica la activa.
- plot('x', 'y') -> dibuja una linea continua definida por los valores de los vectores x e y
- stem('x', 'y') -> dibuja puntos en las posiciones indicadas por los vectores x e y
- hold on -> mantiene lo ya dibujado en la figura activa ante nuevos dibujos
- hold off -> contrarresta hold on