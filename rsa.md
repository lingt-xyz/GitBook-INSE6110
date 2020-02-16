# RSA

## Algorithm

* Based on intractability of the integer factor factorization problem
* $$p,q$$: a large prime integer, _**private**_
* $$N=pq$$, $$N$$is _**public**_
* _\*\*\*\*_$$\Phi(N)=(p-1)(q-1)$$, $$\Phi(N)$$is _**public**_
* Select a random integer $$e: 1< e < \Phi(N) $$
  * gcd$$(e,\Phi(N))=1$$
* Use extended Euclidean algorithm to computer the unique integer $$d,1< d <\Phi(N)$$, such that $$ed\equiv1\mod{\Phi(N)}$$.
* Keys
  * Public key is $$(e,N)$$.
  * Private key is $$d$$.

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

