# RSA de libro

GenRSA(1n):  Genera al azar dos primos p, q de n bits

N=pq&#x20;

ϕ(N)=(p-1)(q-1), elige "e" tal que mcd(e, ϕ(N))=1&#x20;

&#x20;Calcula d=\[e-1 mod ϕ(N)]&#x20;

Devuelve (N, e, d)

Enc(m)=\[me mod N], donde m ϵ ZN

Dec(c)=\[cd mod N], donde c ϵ ZN

Esta definición es insegura y no debe usarse, para arreglarlo se ha redefinido varias veces.
