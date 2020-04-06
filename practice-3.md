# Practice 3

## P1

Consider the public key cryptosystem with the encryption function $$e(x)=x(x+B) \pmod {n}$$ where $$B$$ is a part of the public key. Suppose that $$p=199, q=211, n=pq$$, and $$B=1357$$

1. Determine the ciphertext corresponding to the message $$m=32767$$.
2. Determine the 4 plaintexts corresponding to this ciphertext.

#### Solution

1. $$e(m)=m(m+1357)\pmod {199\times211}=32767(32767+1357)\mod 41989=16027$$
2. Use the fact that if $$p=3 \pmod 4$$ then the square root of $$x \pmod p$$ is given by $$x ^{(p+1)/4}$$.

$$
\begin{align}
c&=x^2+Bx\pmod{n}\\
 &\Rightarrow x^2+Bx-c=0\pmod{n} \\
x&=\frac{-b\pm\sqrt{b^2-4ac}}{2a}\pmod{n}\\
&=\frac{-B\pm\sqrt{B^2+4c}}{2}\pmod{n}\\
&=\frac{-1357\pm\sqrt{{1357}^2+4\times16027}}{2}\pmod{pq}\\
&=\frac{-1357\pm\sqrt{1905557}}{2}\pmod{199\times211}\\
&=\frac{-1357\pm\sqrt{16052}}{2}\pmod{199\times211} \end{align}
$$

We need to solve $$\sqrt{16052}\bmod (199\times211)$$and $$2^{-1}\bmod(199\times211)$$

$$
2^{-1}\bmod(199\times211)=20995
$$

$$
\begin{align}&\begin{cases}m_{p}=c^{{\frac {1}{4}}(p+1)}{\pmod {p}}\\m_{q}=c^{{\frac {1}{4}}(q+1)}{\pmod {q}}\end{cases}\\\Rightarrow&\begin{cases}m_{199}={16052}^{{\frac {1}{4}}(199+1)}{\pmod {199}}\\m_{211}={16052}^{{\frac {1}{4}}(211+1)}{\pmod {211}}\end{cases}\\
\Rightarrow&\begin{cases}m_{199}={132}^{50}{\pmod {199}}\\m_{211}={16}^{53}{\pmod {211}}\end{cases}\\\Rightarrow&\begin{cases}m_{199}=172{\pmod {199}}\\m_{211}=4{\pmod {211}}\end{cases}\end{align}
$$

| $$R_i$$ | $$D_i$$ | $$S_i$$ |
| :--- | :--- | :--- |
| 211 |  | 0 |
| 199 | 1 | 1 |
| 12 | 16 | $$0-1\times1=-1$$ |
| 7 | 1 | $$1-(-1)\times16=17$$ |
| 5 | 1 | $$-1-17\times1=-18$$ |
| 2 | 2 | $$17-(-18)\times1=35$$ |
| 1 |  | $$-18-35\times2=-88=a_2$$ |

$$211a_1+199a_2=1\Rightarrow 211a_1-88\times199=1\Rightarrow a_1=83$$

$$
\begin{align}&\begin{cases}m_{199}=172{\pmod {199}}\\m_{211}=4{\pmod {211}}\end{cases}\\
m&=\big(172\times 211 \times {211}^{-1}\bmod 199+4\times 199 \times {199}^{-1}\bmod 211 \big)\bmod 199\times 211 \\
&=\big(172\times 211 \times a_1+4\times 199 \times a_2 \big)\bmod 199\times 211\\
&=\big(172\times 211 \times 83+4\times 199 \times (-88) \big)\bmod 199\times 211\\
&=2958
\end{align}
$$

Then use the CRT to obtain the 4 square roots mod $$n$$. The four possible messages are 21795, 7865, 32767, 18837.

## P2

Consider a $$(4,3)$$ Shamir secret sharing scheme with $$p=17$$. Show how the secret can be recovered from the following shares: $$(1,10), (2,16)$$, and $$(3,2)$$.

#### Solution

Form 3 equations in 3 unknowns. 

$$\begin{cases}10=a_0+a_1+a_2 \pmod {17}\\ 16=a_0+2a_1+4a_2 \pmod {17}\\ 2=a_0+3 a_1+9a_2 \pmod {17}\end{cases}\Rightarrow\begin{cases}a_0=-16\equiv 1\pmod {17}\\a_1=36\equiv 2\pmod {17}\\a_2=-10\equiv 7\pmod {17}\end{cases}$$ 

Thus the secret $$a_0=1$$

## P3

Consider ElGamal signature scheme as described in lecture. In practical applications, explain what the signer should do if $$s$$ turns out to be equal to zero. Why?

#### Solution

Change the random number.

$$s=0\Rightarrow (h(m)-xr)k^{-1}{\pmod {p-1}}=0\Rightarrow x=h(m)\cdot r^{-1}\pmod {p-1}$$

## P4

Suppose that Alice is using the ElGamal Signature Scheme. In order to save time in generating the random numbers $$k$$ that are used to sign messages, Alice chooses an initial random value $$k_0$$ and then signs the $$i$$th message using the value $$k_i=k_0+2i \pmod p$$ \(therefore $$k_i=k_{i-1} + 2 \pmod p$$ for all $$i\geq1$$. Suppose that an attacker observes two consecutive signed messages, say $$\big(m_i,\text{sig}(m_i)\big)$$ and$$\big (m_{i+1},\text{sig}(m_{i+1})\big)$$. Given this information, describe how the attacker can easily compute Alice’s secret key $$x$$.

$$
s=\big(m-xr\big)k^{-1}{\pmod {p-1}} \\\Rightarrow\begin{cases}\text{sig}(m_1)=(m_1-xr_1){k_1}^{-1} \pmod {p-1}\\ \text{sig}(m_{2})=(m_{2}-xr_2){k_{2}}^{-1} \pmod {p-1}\end{cases}\\\Rightarrow\begin{cases}{k_1}\cdot\text{sig}(m_1)=(m_1-xr_1) \pmod {p-1}\\ {k_{2}}\cdot\text{sig}(m_{2})=(m_{2}-xr_2) \pmod {p-1}\end{cases}\\\Rightarrow\begin{cases}{k_1}\cdot\text{sig}(m_1)=(m_1-xr_1) \pmod {p-1}\\ ({k_1}+2)\cdot\text{sig}(m_{2})=(m_{2}-xr_2) \pmod {p-1}\end{cases}
$$

Two unknowns $$k_1, x$$, we can solve it directly.

## P5

Show that given a legitimate ElGamal signature $$(s,r)$$ on a given message $$m$$, an attacker can compute a signature on messages of the form: $$m'=(m+bs) a \pmod {p−1}$$, where $$a, b$$ are chosen by the attacker and $$a=g^b\pmod p$$.

#### Solution

Since $$(s,r)$$ is a valid signature on $$m$$, then we have $$g^ m = y^r r^s = g^{xr+sk} \pmod p$$. 

If the attacker chooses $$r'= ar\pmod p, s'=as \pmod {p-1}$$, then $$y^{r'} r'^{s'}= y^{ar} (ar)^{as} = g^{xar} {(g^{b+k})}^{as} = g^{xar+asb+ask}=g^{a(xr+sk)+abs}=g^{m'} \pmod p$$

## P6

Consider an RSA with $$n= 2029039$$. If the attacker observed the following message signature pairs $$(m_1,s_1)=(243, 145634)$$ and $$(m_2,s_2)=(876, 609467)$$. Show how the attacker can forge the signature on the message $$m= 212868$$. 

#### Solution

Observe that $$m=m_1\cdot m_2 \pmod n$$_._ Then $$s= s_1\cdot s_2 \pmod n= 835062$$.



