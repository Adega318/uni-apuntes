En el firewall de control de estados no olvidarse del udp.

# 1.
SSH -v | -vw
- Ficheros de configuración (SSH_KONWN_HOST)
- Cifrado
- Clave pública INPORTANTE (devian.org info del funcionamiento)
- Securizar servicio con túnel SSH, comprobar con tráfico http y en el snifing sale tráfico codificado ssh.
- Montaje directorio compartido (dropbox), generación modificado y borrado
## A)
### Clave publica
Generamos la clave con:
```shell
ssh-keygen -t rsa
```
Enviamos la clave:
```shell
ssh-copy-id -i /root/.ssh/id_rsa.pub lsi@10.11.50.142
```
## B)
Seleccionamos el cifrado con el comando:
```shell
scp -c <cipher> <origen> <destino>
```
Los principales cifrados son:
- aes128-ctr
- aes128-cbc
- aes192-ctr
- aes192-cbc
- aes256-ctr
- aes256-cbc
- blowfish-cbc
- arcfour
- arcfour128
- arcfour256
- cast128-cbc
- 3des-cbc
### Proceso

## C)
## D)
## E)
## F)
# 2.
Apache
- entidad certificadora
	- cert
	- easy-rsa (preferente)
- servidores
	- generar certificado propio.
	- Configuración de las claves privada y pública.
	- Enviar la publica a la entidad certificadora y sellarlo.
	- Usar al pública certificada estipulando el certificador con su clave pública.
- Problemas
	- No haber instalado la entidad certificadora en la máquina.
		- Carpeta de devian de entidades certificadoras
	- Url desconocida.
		- Añadir al fichero de hosts el dominio asociado a la ip
		- APUNTAR TODO CUANDO ESTEMOS CREANDO EL CERTIFICADO.
		- Usualmente el problema es el **canonical name** (no ip).
- Carpeta securizada con https
## A)
## B)
## C)
# 3.
Configuración de VPN
- OpenVpn
	- cliente
	- servidor
		- rango de ips
		- cifrado
		- clave/secreto compartido (Pre-Shared Key), pruebas:
			- ifconfig
			- ping de maquina a maquina
# 5.
# 6.
# 7.
# 8.