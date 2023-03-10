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
PID = spawn(MODULE, FUN, ARGS)
% el tipado de los argumentos es dinamico
```
## Mensajes
```erl
% envio de mensajes
PID! MENSAJE

% función de recivida
receive
	% patern maching
	MENSAJE -> ...
end
% revisara mensajes hata que encuentre un mach, no para
```
### Replying
Para contestar el mensaje debe llevar el Pid del remitente, para ello tenemos:
```erl
PID = self()
```
### Timeout
```erl
receive
	...
after
	TIME ->
		true
end
```
## Server process
### Api
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
### Server process
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
### Echo server
```erl
-module(echo).  
-export([start/0, init/0, echo/2]).

start() ->  
	spawn(echo, init, []).  
echo(Echo_Srv, Msg) ->  
	Echo_Srv ! {echo, Msg, self()},  
	receive  
		{echo_reply, Reply} ->  
			Reply  
	end.  
init() ->  
	loop().

loop() ->  
	receive  
		stop ->  
			ok;  
		{echo, Msg, From} ->  
			From ! {echo_reply, Msg},  
			loop()  
	end.
```
### Hash
```erl
-module(hash).  
-export([start/0, store/3, get/2, del/2, stop/1]). % Api  
-export([init/0]). % For spawn. Separate from  
% the api for clarity


%%% API %%%%  
start() ->  
	spawn(?MODULE, init, []).  
	
store(Hash, Key, Value) ->  
	Hash ! {store, Key, Value}.  
	
get(Hash, Key) ->  
	Hash ! {get, Key, self()},  
	receive  
		{hash_ok, V} ->  
			{ok, V};  
		{hash_error, Reason} ->  
			{error, Reason}  
	end.

del(Hash, Key) ->  
	Hash ! {del, Key}. 
	
stop(Hash) ->  
	Hash ! stop.


%%% Internal functions %%%%%  
init() ->  
	loop([]). 
	 
loop(D) ->  
	receive  
		{store, NK, NV} ->  
			loop([{NK,NV} | del_key(NK,D)]);  
		{get, K, From} ->  
			From ! find(K, D),  
			loop(D);  
		{del, KD} ->  
			loop(del_key(KD, D));  
		stop ->  
			ok  
	end.

del_key(K, D) ->  
	[{Key, Val} || {Key,Val} <- D, Key/=K].

find(_, []) -> {hash_error, not_found};  

find(K, [{K,V} | _]) -> {hash_ok, V};  

find(K, [_|T]) -> find(K, T).
```
### Registro
```erl
% definimos NOMBRE como el valor PID
register(NOMBRE, PID),
...

...
NOMBRE!MENSAJE
```
## Errors
### Links
Enlace bidireccional entre procesos, llevándose al resto si uno muere y no se captura la señal de muerte.
```erl
link(PID)
spawn_link(MODULE, FUN, ARGS)
unlink(PID)
```
### Signals
#### Exit
```erl
% tremina con REASON
exit(REASON)

% termina el proceso PID con REASON
exit(PID, REASON)
```
#### Trap_exit
Permite atrapar la finalización de procesos.
```erl
process_flag(MENSAJE, true)
% el formato del MENSAJE es {'EXIT', PID, REASON}
```
## Distribución
### Nodos
```erl
% iniciar
$ erl -name NOMBRE
```
#### Comunicación
```erl
PID=spawn('NOMBRE@MAQUINA', )
```
#### Monitorizar
```erl
monitor_node(NOMBRE, BOOL)

```
# Tags
#2- 
#2-2 
#cp 