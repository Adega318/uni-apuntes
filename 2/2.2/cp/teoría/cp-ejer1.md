# 3. Futures
```C
struct future *promise(void *(*f)(void *), void *arg){  
	struct future *future = malloc(sizeof()struct future));  
	if (!future) return NULL;  
	future->f = f;  
	future->arg = arg;  
	return future;  
}  
void *force(struct future *future){  
	assert(future);  
	future->result = future->f(future->arg);  
	return future->result;  
}  
void free_future(struct future *future){  
	assert(future);  
	free(future);  
}
```
# Tags
#2-
#2-2
#cp