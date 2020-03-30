# Rabin Public Key Encryption

The **Rabin cryptosystem** is an asymmetric [cryptographic](https://en.wikipedia.org/wiki/Cryptographic) technique, whose security, like that of [RSA](https://en.wikipedia.org/wiki/RSA_%28algorithm%29), is related to the difficulty of [integer factorization](https://en.wikipedia.org/wiki/Integer_factorization).

{% hint style="info" %}
So attacks on RSA can be applied on Rabin cryptosystem.
{% endhint %}

{% embed url="https://en.wikipedia.org/wiki/Rabin\_cryptosystem" %}

## Key generation

* $$p,q$$: large prime integers, such that $$p\equiv3\pmod4$$and $$q\equiv3\pmod4$$; _**private**_
* $$N$$: compute$$N=pq$$; _**public**_

## Encryption: 

$$c=m^2\pmod N$$

## Decryption: 

$$m=\sqrt{c}\pmod N$$

The message $$m$$ can be recovered from the ciphertext $$c$$ by taking its square root modulo $$n$$ as follows.

1. Compute the square root of $$c$$ modulo $$p$$ and $$q$$ using these formulas:$$\begin{aligned}m_{p}&=c^{{\frac {1}{4}}(p+1)}{\bmod {p}}\\m_{q}&=c^{{\frac {1}{4}}(q+1)}{\bmod {q}}\end{aligned}$$.
2. Use the [extended Euclidean algorithm](https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm) to find $$a_1$$ and $$a_2$$ such that $$a_1\cdot p+a_2\cdot q=1$$.
3. Use the [Chinese remainder theorem](https://inse6110.lingt.xyz/chinese-remainder-theorem) to find the four square roots of $$c$$ modulo $$n$$:$$ {\begin{aligned}r_{1}&=\left(a_1\cdot p\cdot m_{q}+a_2\cdot q\cdot m_{p}\right){\bmod {n}}\\r_{2}&=n-r_{1}\\r_{3}&=\left(a_1\cdot p\cdot m_{q}-a_2\cdot q\cdot m_{p}\right){\bmod {n}}\\r_{4}&=n-r_{3}\end{aligned}}$$

One of these four values is the original plaintext$$m$$, although which of the four is the correct one cannot be determined without additional information.

## Finding square root$$\pmod N$$

Given $$c$$, finds out $$x$$ such that $$x^2 = c \pmod N$$.

$$\big(c^{ (p+1)/4}\big )^ 2\equiv  c^{ (p+1)/2}\equiv c^{ (p-1)/2}\cdot c\equiv c \pmod p$$

The last step is justified by [Euler's criterion](https://inse6110.lingt.xyz/eulers-criterion).

