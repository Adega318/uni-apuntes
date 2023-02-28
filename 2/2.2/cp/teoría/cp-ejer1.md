# 3. Futures
```C
struct future {  
	void *(*f)(void*);
	void *arg;
	thrd_t thr;
	bool done;
	mtx_t done_m;
	cnd_t not_done;
	void *res;
};
struct future *promise(void *(*f)(void *), void *arg){  
	struct future *future = malloc(sizeof()struct future));  
	if (!future) return NULL;
	future->f = f;
	future->arg = arg;
	future->done = false;
	mtx_create(&future->done_m, mtx_plain)
	cnd_init(&future->not_done);
	thr_create(&future->thr, Do_f, future)
	return future;
}  
int Do_f(void * arg){
	struct future *fut = arg;
	void *res = fut->f(fut->arg);
	mtx_lock(fut->done_m);
	fut->done = true;
	fut->res=res;
	cnd_broadcast(fut->)
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