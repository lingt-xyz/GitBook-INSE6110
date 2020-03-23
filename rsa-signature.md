# RSA Signature

## Key generation

As in RSA encryption:

* $$p,q$$: large prime integers, _**private**_
* $$N$$: compute$$N=pq$$, _**public**_
* _\*\*\*\*_$$\Phi(N)$$: compute $$\Phi(N)=(p-1)(q-1)$$, _**private**_
* $$e$$: choose a random integer $$e: 1< e < \Phi(N) $$, such that gcd$$(e,\Phi(N))=1$$, _**public**_
* $$d$$: determine the unique integer $$d:1< d <\Phi(N)$$, such that $$ed\equiv1\mod{\Phi(N)}$$, _**private**_

Public key: $$(e, N)$$ 

Secret key: $$d$$. $$p$$ and $$q$$ must also remain secret.

## RSA Signature





