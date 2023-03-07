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
[Pid] = spawn([Module], [Fun], [Args])
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
Server api:
```erl
-module(server).
-export([async_req1/...,sync_req2/...]).

start() -> spawn(Module, init, [...]).

% API that abstracts the communication with
% the server to the clients
async_req1(Serv, ...) ->
	Serv ! {req1, ...}.
	
sync_req2(Serv, ...) ->
	Serv ! {req2, ... , self()},
	receive
		{req2_reply, ...} ->
		...
	end.
```
Server (en un proceso), donde haremos empleo de un loop (recursivo) que tiene que ser terminal.
```erl
init(...) ->
	<initialization>,
	loop(...).

% el estado del loop se pasa en los parametros de la recursividad
loop(...) ->
	receive
		stop -> true; 
			% no recursive call => exit
		{req1, ...} ->
			<serve req1>
			loop(...);
		...
		{req2, ..., From} ->
			<serve req2>
			From ! {req2_reply, ...},
			loop(...)
	end. 
```