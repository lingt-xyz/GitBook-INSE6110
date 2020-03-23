# Practice 3

## P1

Consider the public key cryptosystem with the encryption function $$e(x)=x(x+B) \pmod {n}$$ where $$B$$ is a part of the public key. Suppose that $$p=199, q=211, n=pq$$, and $$B=1357$$

1. Determine the ciphertext corresponding to the message $$m=32767$$.
2. Determine the 4 plaintexts corresponding to this ciphertext.

#### Solution

1. $$e(m)=m(m+1357)\pmod {199\times211}=32767(32767+1357)\mod 41989=16027$$
2. Use the fact that if $$p=3 \pmod 4$$ then the square root of $$x \pmod p$$ is given by $$x ^{(p+1)/4}$$.

$$
c=x^2+Bx\pmod{n} \Rightarrow x^2+Bx-c=0\pmod{n}
$$

$$
\begin{align}
x&=\frac{-b\pm\sqrt{b^2-4ac}}{2a}\pmod{n}\\
&=\frac{-B\pm\sqrt{B^2+4c}}{2}\pmod{n}\\
&=\frac{-1357\pm\sqrt{{1357}^2+4\times16027}}{2}\pmod{n}\\
&=\frac{-1357\pm\sqrt{1905557}}{2}\pmod{n}\end{align}
$$

$$
\begin{cases}m_{p}&=c^{{\frac {1}{4}}(p+1)}{\pmod {p}}\\m_{q}&=c^{{\frac {1}{4}}(q+1)}{\pmod {q}}\end{cases}\Rightarrow\begin{cases}m_{199}&={1905557}^{{\frac {1}{4}}(199+1)}{\pmod {199}}\\m_{211}&={1905557}^{{\frac {1}{4}}(211+1)}{\pmod {211}}\end{cases}
$$

Then use the CRT to obtain the 4 square roots mod $$n$$. The four possible messages are 21795, 7865, 32767, 18837.

## P2

Consider a $$(4,3)$$ Shamir secret sharing scheme with $$p=17$$. Show how the secret can be recovered from the following shares: $$(1,10), (2,16)$$, and $$(3,2)$$.

#### Solution

Form 3 equations in 3 unknowns. 

$$\begin{cases}10=a_0+a_1+a_2 \pmod {17}\\ 16=a_0+2a_1+4a_2 \pmod {17}\\ 2=a_0+3 a_1+9a_2 \pmod {17}\end{cases}\Rightarrow\begin{cases}a_0=1\\a_1=2\\a_2=7\end{cases}$$ 

Thus the secret $$a_0=1$$

## P3

Consider ElGamal signature scheme as described in lecture. In practical applications, explain what the signer should do if “S” turns out to be equal to zero. Why?

#### Solution

Change the random number.

$$S'=0\Rightarrow h(m)-xr=0\Rightarrow x=h(m)\cdot r^{-1}\pmod {p-1}$$

## P4

Suppose that Alice is using the ElGamal Signature Scheme. In order to save time in generating the random numbers $$k$$ that are used to sign messages, Alice chooses an initial random value $$k_0$$ and then signs the $$i$$th message using the value $$k_i=k_0+2i \pmod p$$ \(therefore $$k_i=k_i-1 + 2 \pmod p$$ for all $$i\geq1$$. Suppose that an attacker observes two consecutive signed messages, say $$\large(x_i,sign(x_i)\large)$$ and$$\large (x_i+1,sign(x_i+1)\large)$$. Given this information, describe how the attacker can easily compute Alice’s secret key $$a$$.

## P5

Show that given a legitimate ElGamal signature $$(s,r)$$ on a given message $$m$$, an attacker can compute a signature on messages of the form: $$m'=(m+bs) a \pmod {p−1}$$, where $$a, b$$ are chosen by the attacker and $$a=g^b\pmod p$$.

#### Solution

Since $$(s,r)$$ is a valid signature on $$m$$, then we have $$g^ m = y^r r^s = g^{xr+sk} \pmod p$$. 

Now to forge the signature on $$m'$$, we need to have $$g^{m'} = g^{am+abs}\pmod p=g^{a(xr+sk)+abs}=g^{axr+ask+abs} \pmod p = y^{r'} r'^{s'} \pmod p$$.

By comparing both sides, we have $$r'= ar \pmod p=g^{k+b} \pmod p$$, $$s'=as \pmod {p-1}$$.

You can verify that it works by doing the following: $$y^{r'} r'^{s'} = y^{ra} r'^{as} = g^{xra} {g^{k+b}}^{as'} = g^{xra+ask+asb}=g^{m'} \pmod p$$

## P6

Consider an RSA with $$n= 2029039$$. If the attacker observed the following message signature pairs $$(m_1,s_1)=(243, 145634)$$ and $$(m_2,s_2)=(876, 609467)$$. Show how the attacker can forge the signature on the message $$m= 212868$$. 

#### Solution

Observe that $$m=m_1\cdot m_2 \pmod n$$_._ Then $$s= s_1\cdot s_2 \pmod n= 835062$$.



