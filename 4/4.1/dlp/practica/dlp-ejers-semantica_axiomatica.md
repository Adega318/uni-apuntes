```
{m>=0}
f=1
i=1
{f=i! & i<=m}
while i<m
	{f=i! & i<n}
	i=i+1
	f=f*i
{f=i! & i=m}
{f=n!}
```

| i   | f       |
| --- | ------- |
| 1   | 1       |
| 2   | 1\*2    |
| 3   | 1\*2\*3 |

# Ejer serie de fibonachi
```
{n>=0}

fib0 = 0
fib1 = 1
k = n

while k>0
	aux = fib0
	fib0 = fib1
	fib1 = fib1 + aux
	k = k - 1
{I & k=0}

{fib0 = Fib(n)}
```


| k   | fib0 | fib1 |
| --- | ---- | ---- |
| n   | 0    | 1    |
| n-1 | 1    | 1    |
| n-2 | 1    | 2    |


```
{n>=0}

fib0 = 0
fib1 = 1
k = n

while k>0
	aux = fib0
	fib0 = fib1
	fib1 = fib1 + aux
	k = k - 1
{fib0 = Fib(n-k) & fib1 = Fib(n-k+1) & k=0}

{fib0 = Fib(n)}
```