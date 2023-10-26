# Formatos
## XML
Lenguaje de etiquetas personales, con la siguiente sintaxis:
- tags, \<tag>\</tag>
- atributos, información sobre una tag \<tag atributo= x>
- comentarios, \<!-- hfak --\>

### Documento
Secuencia de caracteres con formato XML
### Aplicación
Conjunto de tags para representar  información, siguiendo las siguientes reglas:
- Distinción entre mayúsculas.
- Declaración XML, indica información del lenguaje (versión y diccionario).
- Tags multivaluados y atributos únicos.

### Caracteres sensibles
| Referencia | Carácter |
| ---------- | -------- |
| \&lt       | <        |
| \&amp      | &        |
| \&gt       | >        |
| \&quot     | "        |
| \&apos     | '        | 

### Espacio de nombres


## JSON
## Sintaxis
### Tipos
- Objeto, especificado entre llaves {}
- Array, especificado entre corchetes \[\]
- String, especificado entre comillas dobles ""
- Número
- Bool
- Null

### Esquemas
null
```JSON
{"type": "null"}
```
bool
```JSON
{"type": "boolean"}
```
número
```JSON
{
	"type": "integer", //enteros
	"minimun": 100, //minimo
	"maximun": 200 //maximo
} 
```
string
```JSON
{
	"type": "string",
	"minlenght": 4,
	"maxlenght": 10,
	"format": "date_time"
}
```
array
```JSON
{
	"type": "array",
	"items": {
		"type": "string"
		"minlenght"
	}
}
```