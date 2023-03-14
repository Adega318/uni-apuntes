# Monitores
# Memoria transaccional
1. Marcamos regiones como atómicas  
2. Se realizan todas las lecturas y escrituras  
3. Comprueba si algún thread ha cambiado algún valor de los que usamos  
4. Aborta la transacción en caso afirmativo  
5. La termina en caso negativo  
6. Otro thread ve todos los cambios o ninguno
Se suele implementar un retray para cancelar e intentar de nuevo.
Este método permite la composición de funciones, al no hacer empleo de mutex.
# Tags
#2- 
#2-2 
#cp 