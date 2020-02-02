# Chinese Remainder Theorem

## Statement

Let $$p,q$$ be coprime. Then the system of equations

$$
x=a \pmod p\\
x=b \pmod q
$$

has a unique solution for$$x\pmod {pq}$$, which is

$$
x=aqq'+bpp'\pmod{pq}
$$

where $$q'=q^{-1}\pmod{p}$$and $$p'=p^{-1}\pmod{q}$$.

## General form

Let $$m_1,\cdots,m_n$$ be pairwise coprime \(that is $$gcd(m_i,m_j)=1$$ whenever $$i≠j$$\). Then the system of $$n$$ equations

$$
x=a_1\pmod{m_1}\\
x=a_2\pmod{m_2}\\
\cdots\\
x=a_n\pmod{m_n}
$$

has a unique solution for $$x\pmod {m_1m_2\cdots m_n}$$, which is

$$
x=n\sum_{i=1}^{n}{a_ib_ib_i'}\pmod{m_1m_2\cdots m_n}
$$

 where $$b_i = \frac{m_1m_2\cdots m_n}{m_i}$$ and $$b_i' = {b_i}^{-1}\pmod{m_i}$$.

## Examples

### Q1

$$
x=5 \pmod {11}\\
x=3 \pmod 7
$$

$$\begin{align}x&=aqq'+bpp'\pmod{pq}\\ &=5\times7\times\big(7^{-1}\pmod{11}\big)+3\times11\times\big(11^{-1}\pmod{7}\big)\pmod{11\times7}\\ &=5\times7\times8+3\times11\times2 \pmod{11\times7}\\ &=38\pmod{77}\end{align}$$

### Q2

$$
x=5 \pmod {7}\\
x=3 \pmod {11}\\
x=10 \pmod {13}
$$

$$
\begin{cases}
a_1=5,a_2=3,a_3=10\\
m_1=7,m_2=11,m_3=13
\end{cases}\\
\Rightarrow \begin{cases}
b_1=m_2m_3=143 \\
b_2=m_1m_3=91 \\
b_3=m_1m_2=77
\end{cases}
\Rightarrow \begin{cases}
b_1' = {b_1}^{-1}\pmod{m_1} ={143}^{-1}\pmod 7=5\\
b_2' = {b_2}^{-1}\pmod{m_2} =91^{-1}\pmod {11} =4\\
b_3' = {b_3}^{-1}\pmod{m_3} =77^{-1}\pmod {13} =12
\end{cases}
$$

$$\begin{align}x&=n\sum_{i=1}^{n}{a_ib_ib_i'}\pmod{m_1m_2\cdots m_n}\\ &=5\times143\times5+3\times91\times4+10\times77\times12\pmod{7\times11\times13} \\ &=3575+1092+9240\pmod{1001}\\ &=894\end{align}$$

