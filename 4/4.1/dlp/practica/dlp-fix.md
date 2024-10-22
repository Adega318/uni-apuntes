$fix=\lambda f.(\lambda x.f(\lambda y.x xy)(\lambda x.f(\lambda y.x xy)))$

Esto permite substituir las llamadas recursivas de funciones por la propia función.

letrec sum : Nat -> Nat -> Nat = lambda n : Nat. lambda m : Nat. if iszero n then m else succ (sum (pred n) m) in sum 21 34