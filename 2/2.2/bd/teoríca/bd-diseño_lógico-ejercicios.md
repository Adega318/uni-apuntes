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

Paso 4:
Emp
	NumE -> NomE, NumD
Dept
	NumD -> NomD, DirD
	NomD -> NumD, DirD
	DirD -> NumD, NomD
Pro
	CodP -> PresP

Paso 5:
(NumE, CodP)

Paso 6:
Emp
	NumE -> NomE, NumD 2FN
Dept
	NumD -> NomD, DirD 3FN
	NomD -> NumD, DirD 3FN
	DirD -> NumD, NomD 3FN
Pro
	CodP -> PresP 2FN

R1(NumD, NomD, DIrD)
F1{
	NumD -> NomD, DirD
	NomD -> NumD, DirD
	DirD -> NumD, NomD
}
CC1 NumD, CC2 NomD, CC3 DirD
FNBC

R2(NumE, NomE, NumD, CodP, PresP)
F2{
	NumE -> NomE, NumD 
	CodP -> PresP
}
2FN

R3(CodP, PresP)
F3{
	CodP -> PresP
}
FNBC

R2'(NumE, NomE, NumD)
F2'{
	NumE -> NomE, NumD
}
FNBC

R4(NumE, CodP)

**La solución sería**: 
R1(NumE, NomE, NumD)
F1{
	NumE -> NomE, NumD
}CC: NumE

R2(CodP, PresP)
F2{
	CodP -> PresP
}CC: CodP

R3(NumD, NomD, DIrD)
F3{
	NumD -> NomD, DirD
	NomD -> NumD, DirD
	DirD -> NumD, NomD
}CC: NumD

R4(NumE, CodP)
F4{ null }CC: NumE

FNBC

# 3.
Atributos:
- nome_suc: Nome da sucursal  
- cidade_suc: Cidade da sucursal  
- activos_suc: Activos dispoñibles na sucursal para novos empr ́estitos  
- nome_cli: Nome do cliente  
- enderezo_cli: Enderezo do cliente  
- cod_empr: C ́odigo do empr ́estito  
- importe_empr: Importe do empr ́estito

R(nombre_suc, cidade_suc, activos_suc, nome_cil, enderezo_cil, cod_empr, importe_empr)
F{
	nombre_suc -> cidade_suc, activos_suc
	nombre_cil -> enderezo_cil
	cod_empr -> importe_empr, nome_suc
}

**Solución:**
R1(nombre_suc, cidade_suc, activos_suc)
F1{
	nombre_suc -> cidade_suc, activos_suc
}CC: nombre_suc

R2(nombre_cil, enderezo_cil)
F2{
	nombre_cil -> enderezo_cil
}CC: nombre_cil

R3(cod_empr, importe_empr, nome_suc)
F3{
	cod_empr -> importe_empr, nome_suc
}CC: cod_empr

R4(nombre_cil, cod_empr)
F4{null} CC: nombre_cil

# Ejer 7
R=(NHC, NOMEP, AP1P, AP2P, TLF, NSS, NOMEM, AP1M, AP2M, DATA CITA, HORA  
CITA, LUGAR, MEDICAMENTO, DOSE, DURACION)

Paciente:
- NHC -> NOMEP, AP1P, AP2P, TLF
Médico:
- NSS -> NOMEM, AP1M, AP2M
Centro:
- LUGAR
Medicamento:
- MEDICAMENTO
Citas:
- DATA CITA, HORA CITA



# Tags
#2- 
#2-2 
#bd