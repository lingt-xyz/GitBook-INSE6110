# Practice 1

## Q1

Let $$A=\begin{bmatrix}     11 & 12 \\    71 & 33 \\  \end{bmatrix}$$, find $$A^{-1}$$over $$Z_5$$.

## Q2

### A1\) 

$$gcd(621, 345)=69$$

| $$R_i$$ | $$D_i$$ |
| :--- | :--- |
| 621 |  |
| 345 | 1 |
| 276 | 1 |
| 69 | 4 |
| 0 |  |

### A2\) 

$$gcd(11316,1221)=3$$

| $$R_i$$ | $$D_i$$ |
| :--- | :--- |
| 11316 |  |
| 1221 | 9\(10989\) |
| 327 | 3\(981\) |
| 240 | 1 |
| 87 | 2\(174\) |
| 66 | 1 |
| 21 | 3 |
| 3 | 7 |
| 0 |  |

### A3\)

$$gcd(115,391)=23$$

| $$R_i$$ | $$D_i$$ |
| :--- | :--- |
| 391 |  |
| 115 | 3\(345\) |
| 46 | 2\(92\) |
| 23 | 2 |
| 0 |  |

### A4\)

$$gcd(1110, 3195)=15$$

| $$R_i$$ | $$D_i$$ |
| :--- | :--- |
| 3195 |  |
| 1110 | 2\(2220\) |
| 975 | 1 |
| 135 | 7\(945\) |
| 30 | 4\(120\) |
| 15 | 2 |
| 0 |  |

### B1\) 

$${23}^{-1}\bmod 67\equiv -32\bmod67\equiv35$$

| $$R_i$$ | $$D_i$$ | $$S_i$$ |
| :--- | :--- | :--- |
| 67 |  | 0 |
| 23 | 2\(46\) | 1 |
| 21 | 1 | $$0-1\times2=-2$$ |
| 2 | 10 | $$1-(-2)\times1=3$$ |
| 1 |  | $$-2-3\times10=-32$$ |

### B2\) 

$${32}^{-1}\bmod 167\equiv47$$

| $$R_i$$ | $$D_i$$ | $$S_i$$ |
| :--- | :--- | :--- |
| 167 |  | 0 |
| 32 | 5\(160\) | 1 |
| 7 | 4\(28\) | $$0-1\times5=-5$$ |
| 4 | 1 | $$1-(-5)\times4=21$$ |
| 3 | 1 | $$-5-21\times1=-26$$ |
| 1 |  | $$21-(-26\times1)=47$$ |

### B3\) 

$${111}^{-1}\bmod 143\equiv67$$

| $$R_i$$ | $$D_i$$ | $$S_i$$ |
| :--- | :--- | :--- |
| 143 |  | 0 |
| 111 | 1 | 1 |
| 32 | 3\(96\) | $$0-1\times1=-1$$ |
| 15 | 2 | $$1-(-1)\times3=4$$ |
| 2 | 7 | $$-1-4\times2=-9$$ |
| 1 |  | $$4-(-9\times7)=67$$ |

### B4\) 

$${3}^{-1}\bmod 17\equiv6$$

| $$R_i$$ | $$D_i$$ | $$S_i$$ |
| :--- | :--- | :--- |
| 17 |  | 0 |
| 3 | 5 | 1 |
| 2 | 1 | $$0-1\times5=-5$$ |
| 1 |  | $$1-(-5)\times1=6$$ |

### B5\) 

$${114}^{-1}\bmod 115\equiv -1\bmod115=114$$

| $$R_i$$ | $$D_i$$ | $$S_i$$ |
| :--- | :--- | :--- |
| 115 |  | 0 |
| 114 | 1 | 1 |
| 1 |  | $$0-1\times1=-1$$ |

### C\)

Using the square and multiply algorithm to evaluate $${123}^{20}\bmod129$$.

$${123}^{20}={123}^{16}\times{123}^{4}$$

$$\begin{align} &{123}^{4}\bmod129\equiv6\\\Rightarrow&{123}^{8}\bmod129\equiv36\bmod129=36\\\Rightarrow&{123}^{16}\bmod129\equiv {36}^2\bmod129=6\end{align}$$

$${123}^{20}\bmod129\equiv6\times6\bmod129=36$$

## Q3

Factor $$N=26797$$using the fact that $$\Phi(N)=26460$$.

$$\begin{cases}  N=26797=pq\\  \Phi(N)=26460=(p-1)(q-1)\end{cases}\Rightarrow\begin{cases}  p=\frac{26797}{q}\\  (\frac{26797}{q}-1)(q-1)=26460\end{cases}$$

$$\begin{align} &(\frac{26797}{q}-1)(q-1)=26460\\ \Rightarrow  &(26797-q)(q-1)=26460q \\ \Rightarrow  &26797q-q^2-26797+q=26460q \\ \Rightarrow  &q^2-338q+26797=0 \end{align}$$

$$
\begin{align}
&q=\frac{-b\pm\sqrt{b^2-4ac}}{2a}\\
\Rightarrow&q=\frac{338\pm\sqrt{(-338)^2-4\times1\times26797}}{2\times1}\\
\Rightarrow&q=\frac{338\pm84}{2}\\
\Rightarrow&q=127,211\\
\end{align}
$$

## Q4

### A\)

Let $$p=123456791$$. Find $${123}^{123456790}\bmod123456791$$.

According to Fermat's little Theorem:

$$
a^{p − 1}\equiv 1\pmod p\Rightarrow {123}^{123456790}\bmod123456791\equiv1
$$

### B\)

From the information provided in Q3, find $$3^{26460}\bmod26797$$.

According to Euler's Theorem:

$$
\begin{align}
&a^{\Phi(N)}\equiv 1\pmod N\\
\text{and}&\\&{\Phi(N)}\equiv (p-1)(q-1)\text{ for }N=pq
\end{align}
$$

$$\Rightarrow3^{26460}\bmod26797\equiv1$$

## Q5

### A\)

$$
\begin{align}
x&=3\bmod7\\
x&=5\bmod11\\
x&=9\bmod13
\end{align}
$$

$$a_1=3,a_2=5,a_3=9,m_1=7,m_2=11,m_3=13$$

$$\begin{align}x&=\sum_{i=1}^{n}{a_ib_ib_i'}\pmod{m_1m_2\cdots m_n}\\ &=\Big(3\times(11\times13)\times\big((11\times13)^{-1}\bmod7\big)\\ &\  +5\times(7\times13)\times\big((7\times13)^{-1}\bmod11\big)\\ &\ +9\times(7\times11)\times\big((7\times11)^{-1}\bmod13\big)\Big)\bmod(7\times11\times13)\\ &=  \end{align}$$

### B\)

$$
\begin{align}
x&=2\bmod7\\
x&=3\bmod11
\end{align}
$$

### C\)

$$
\begin{align}
x&=11\bmod19\\
x&=12\bmod23
\end{align}
$$

### D\)

$$
\begin{align}
x&=1\bmod19\\
x&=2\bmod23\\
x&=3\bmod17
\end{align}
$$

## Q6-1

Let $$p=19$$ and $$q=29$$. Let $$N=p×q$$. Find $$d=5^{-1} \pmod {\Phi(N)}$$. Ans.$$d=101$$

## Q6-2

$${11}^5\bmod {551}\equiv( {11}^4\bmod {551}\times {11}^1\bmod {551})\bmod {551}$$

## Q6-3

$${159}^{101}\pmod{551}$$

$${159}^{101}= {159}^{64}\times {159}^{32}\times {159}^{4}\times {159}^{1}$$

$$\Rightarrow$$

$${159}^1\pmod{551}=159$$

$$159^{4}\pmod {551}= 368$$

$$159^{8}\pmod {551}= (159^{4})^2\pmod {551}= {368}^2\pmod{551}=429$$

$$159^{16}\pmod {551}= (159^{8})^2\pmod {551}= {429}^2\pmod{551}=7$$

$$159^{32}\pmod {551}= (159^{16})^2\pmod {551}= {7}^2\pmod{551}=49$$

$$159^{64}\pmod {551}= (159^{32})^2\pmod {551}= {49}^2\pmod{551}=197$$

$$\Rightarrow$$

$${159}^{101}\pmod{551}={197\times49\times368\times159}\pmod{551}=11$$

