# 3. Futures
```c
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
	void *res = fut->f(fut->arg); //f hace lo que toca
	mtx_lock(fut->done_m);
	fut->done = true;
	fut->res=res;
	cnd_broadcast(fut->not_done);
	mtx_unlock(fut->done_m);
}

void *force(struct future *future){  
	mtx_lock(future->done_m);
	if(!future->done) cnd_wait(future->not_done, future->done_m);
	void *res = future->res;
	mtx_unlock(future->done_m);
	return future->result;
}  

void free_future(struct future *future){  
	cnd_destroy(future->not_done);
	mtx_destroy(future->done_m);
	free(future);
}
```
# Tags
#2-
#2-2
#cp