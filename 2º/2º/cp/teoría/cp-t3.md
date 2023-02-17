# Descripción
# Buffer limitado
```
mtx block
```
## Productor
```
while(1){
	elemento e = crear_elemento()
	int inserted = 0
	do{
		lock(block)
		if(elements() < buffer_size()){
		
		}
	}
}
```
## Consumidor