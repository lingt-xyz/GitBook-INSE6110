# Practice 3

## P1

Consider the public key cryptosystem with the encryption function $$e(x)=x(x+B) \pmod {n}$$ where $$B$$ is a part of the public key. Suppose that $$p=199, q=211, n=pq$$, and $$B=1357$$

1. Determine the ciphertext corresponding to the message $$m=32767$$.
2. Determine the 4 plaintexts corresponding to this ciphertext.

Solution

1. $$e(m)=m(m+1357)\pmod {199\times211}=32767(32767+1357)\mod 41989$$
2. $$\begin{align}&c=x^2+Bx\pmod{n}\\ \Rightarrow &x^2+Bx-c=0\pmod{n}\\ \Rightarrow&x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}\pmod{n}\end{align}$$



