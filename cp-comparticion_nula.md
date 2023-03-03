La compartición nula se basa en el paso de mensajes.
# Almacenamiento de mensajes
- Directa, no se almacenan mensajes, parando el programa hasta que lo enviado se reciba.
- Cola, los mensajes se almacenan en una cola y retiran en orden de llegada.
- Mailbox, los mensajes se almacenan y se pueden retirar en el orden deseado (multiples enviadores).
# Primitivas
Tendremos dos primitivas, envió y recibir. Podemos tener dos tipos de comportamiento:
- Síncrono, bloquea el proceso de envío.
- Asíncrono, no se espera a la lectura.
# Erlang
