# Practice 3

## P1

Consider the public key cryptosystem with the encryption function $$e(x)=x(x+B) \pmod {n}$$ where $$B$$ is a part of the public key. Suppose that $$p=199, q=211, n=pq$$, and $$B=1357$$

1. Determine the ciphertext corresponding to the message $$m=32767$$.
2. Determine the 4 plaintexts corresponding to this ciphertext.

Solution

1. $$e(m)=m(m+1357)\pmod {199\times211}=32767(32767+1357)\mod 41989$$
2. $$c=x^2+Bx\pmod{n} \Rightarrow x^2+Bx-c=0\pmod{n} \Rightarrow x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}\pmod{n}$$. Use the fact that if $$p=3 \pmod 4$$ then the square root of $$x \pmod p$$ is given by $$x ^{(p+1)/4}$$. Then use the CRT to obtain the 4 square roots mod $$n$$. The four possible messages are 21795, 7865, 32767, 18837.

## P2

## P3

Consider ElGamal signature scheme as described in lecture. In practical applications, explain what the signer should do if “S” turns out to be equal to zero. Why?



## P4

## P5

## P6

Consider an RSA with $$n= 2029039$$. If the attacker observed the following message signature pairs $$(m_1,s_1)=(243, 145634)$$ and $$(m_2,s_2)=(876, 609467)$$. Show how the attacker can forge the signature on the message $$m= 212868$$. 

Solution: Observe that $$m=m_1\cdot m_2 \pmod n$$_._ Then $$s= s_1\cdot s_2 \pmod n= 835062$$.



