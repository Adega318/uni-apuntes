La compartición nula se basa en el paso de mensajes.
# Almacenamiento de mensajes
- Directa, no se almacenan mensajes, parando el programa hasta que lo enviado se reciba.
- Cola, los mensajes se almacenan en una cola y retiran en orden de llegada.
- Mailbox, los mensajes se almacenan y se pueden retirar en el orden deseado (múltiples enviadores).
# Primitivas
Tendremos dos primitivas, envió y recibir. Podemos tener dos tipos de comportamiento:
- Síncrono, bloquea el proceso de envío.
- Asíncrono, no se espera a la lectura.
# Erlang
Erlang maneja los procesos usando la compartición mula, mandando mensajes entre ellos.
```erl
% create a new process
[Pid] = spawn([Module], [Fun], [Args]).
% el tipado de los argumentos es dinamico
```
## Mensajes
```erl
% envio de mensajes
[Pid]! [Mensaje]

% función de recivida
receive
	% patern maching
	[Mensaje] -> ...
end
% revisara mensajes hata que encuentre un mach, no para
```
### Replying
Para contestar el mensaje debe llevar el Pid del remitente, para ello tenemos:
```erl
[Pid] = self()
```
## Server process
