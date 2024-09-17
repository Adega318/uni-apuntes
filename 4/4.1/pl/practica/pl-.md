# Herramientas
- LEX, herramienta de diseño de procesadores de lenguaje.
	- FLEX, derivación de LEX.

```
fichero.l -> FLEX -> lex.yy.c -> GCC -> a.out
```

# Expresiones regulares
a|b -> a, b
ab -> ab
a* -> $\epsilon$, a, aa, aaa, ...
a+ -> a, aa, aaa, ...
ab? -> a, ab
. -> un elemento de cualquier tipo.
a$ -> búsqueda de elemento al final de linea
## Agrupaciones de elementos
\[a e i o u\] -> vocales (solo encaja el primero que encuentre)
\[A-Z\] -> Las mayúsculas de la A a la Z
\[a-zA-Z\] -> Letras
\[A-ZÁÉÍÓÚÑ\]