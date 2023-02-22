# Ejers clase teórica 15/02/23
Dado el esquema relacional R(A,B,C,D,E) (ejer 1 boletín).
## 1.
Enunciado:
F= (
CD-E
C-A
A-B
E-C)

Resultado:
CC:
{CD} = {ABCDE}
{ED} = {ABCDE}
FN:
1FN //suponemos atributos atómicos
2FN //no cumple la segunda a causa de que A y no depende del conjunto de las candidatas.
## 2.
Enunciado:
F=(
DA-C
DA-B
B-E
C-D)

Resultado:
CC:
{DA} = {ABCDE}
{CA} = {ABCDE}
FN:
1FN //suponemos atributos atómicos
2FN //todos los primos no dependen de ninguna parte concreta de la candidata
3FN //E, primo depende de una no clave candidata
## 3.
Enunciado:
F = (
AC-B
AC-D
C-E
E-C)

Resultado:
CC:
{AC} = {ABCDE}
{AE} = {ABCDE}
FN:
1FN //suponemos atómicos
2FN //No hay no primas dependientes de parte de la candidata
3FN //No hay no primos que dependan de la candidata transitivamente
FNBC //No toda relación tiene en la izquierda la candidata
## 4.
Enunciado:
F = (
AB-E
AB-C
AB-D
CD-A
CD-B)

Resultado:
CC:
{AB} = {ABCDE}
{CD} = {ABCDE}
FN:
1FN //suponemos atómicos
2FN //No hay no primas dependientes de parte de la candidata
3FN //No hay no primos que dependan de la candidata transitivamente
FNBC //Toda relación tiene en la izquierda la candidata
# Ejers clase teórica 22/02/23
Datos del ejer 2 boletín:
R(NumE, NomE, NumD, NomD, DirD, CodP, PresP)
## 1.
Pasos del 1 al 3:
Emp
	NumE -> NomE
Dept
	NumD -> NomD, DirD
	NomD -> NumD, DirD
	DirD -> NumD, NomD
Pro
	CodP -> PresP

# Tags
#2- 
#2-2 
#bd