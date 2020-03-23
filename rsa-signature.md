# RSA Signature

## Key Generation

As in RSA encryption:

* $$p,q$$: large prime integers, _**private**_
* $$N$$: compute$$N=pq$$, _**public**_
* _\*\*\*\*_$$\Phi(N)$$: compute $$\Phi(N)=(p-1)(q-1)$$, _**private**_
* $$e$$: choose a random integer $$e: 1< e < \Phi(N) $$, such that gcd$$(e,\Phi(N))=1$$, _**public**_
* $$d$$: determine the unique integer $$d:1< d <\Phi(N)$$, such that $$ed\equiv1\mod{\Phi(N)}$$, _**private**_

Public key: $$(e, N)$$ 

Secret key: $$d$$. $$p$$ and $$q$$ must also remain secret.

## RSA Signature

1. Signing the message $$m$$
   * Use private key $$d$$, compute $$S_d=m^d\pmod N$$.
2. Verifying signature$$S$$
   * User public key $$(e,N)$$, compute $$S_e=\big(m^d\pmod N\big)^e\pmod N=m$$

{% hint style="warning" %}
* Should sign the message $$m$$ or sign the hash $$h(m)$$?
{% endhint %}

## Cryptanalysis

### Multiplicative property

See [https://inse6110.lingt.xyz/practice-3\#p6](https://inse6110.lingt.xyz/practice-3#p6)

Sign $$h(m)$$to prevent this attack.

## Sign First or Encrypt First

In practical, both message and signature should be encrypted.

But we have options to sign first or encrypt first.

1. If$$N_A<N_B$$, Alice should sign first.
   * Alice:
     * $$c_1=m^{d_A}\pmod {N_A}$$
     * $$c_2=m^{e_B}\pmod {N_B}$$
   * Bob:
     * $$c_1=(c_2)^{d_B}\pmod {N_B}$$
     * $$m=c_1^{e_A}\pmod {N_A}$$

