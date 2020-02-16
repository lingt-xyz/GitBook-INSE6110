# RSA

Invented in 1978 by Ron **R**ivest, Adi **S**hamir and Leonard **A**dleman.

Invented in 1978 by Ron **R**ivest, Adi **S**hamir and Leonard **A**dleman.

## Algorithm

Based on intractability of the integer factor factorization problem.

## Algorithm

* $$p,q$$: a large prime integer, _**private**_
* $$N$$: compute$$N=pq$$, _**public**_
* _\*\*\*\*_$$\Phi(N)$$: compute $$\Phi(N)=(p-1)(q-1)$$, _**private**_
* $$e$$: choose a random integer $$e: 1< e < \Phi(N) $$, such that gcd$$(e,\Phi(N))=1$$, _**public**_
* $$d$$: determine the unique integer $$d:1< d <\Phi(N)$$, such that $$ed\equiv1\mod{\Phi(N)}$$, _**private**_

## Encryption

* How it works
  * Bob encryption
    1. Get Alice's authentic public key $$(e,N)$$
    2. Computer $$c=m^e\mod N$$.
    3. Send $$c$$ to Alice.
  * Alice decryption
    1. Compute $$m=c^d\mod N$$.
* Why it works
  1. Since $$ed\equiv1\mod{\Phi(N)}$$, there exists an integer $$k$$ such that $$ed\equiv1+k\cdot \Phi(N)$$
  2. $$c^d=m^{ed}=m^{1+k\cdot \Phi(N)}=m^1\cdot m^{k\cdot \Phi(N)}=m^1\cdot (m^{\Phi(N)})^k=m^1\cdot (1)^k=m$$

