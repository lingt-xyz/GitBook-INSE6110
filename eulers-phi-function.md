# Euler's phi function

## Definition 

Euler's phi \(or totient\) function of a positive integer $$n$$ is the number of integers in $$\{1,2,3,...,n\}$$ which are relatively prime to $$n$$. This is usually denoted $$\Phi(n)$$. For a prime number $$p$$,

$$
\Phi(p)=p-1
$$

If $$p,q$$are prime numbers, and $$N=pq$$,

$$
a^{\Phi(N)}\equiv (p-1)(q-1)
$$

If $$gcd(a,p)=1$$,

$$
a^{\Phi(p)}\equiv 1\pmod p
$$

## General form

The [fundamental theorem of arithmetic](https://en.wikipedia.org/wiki/Fundamental_theorem_of_arithmetic) states that if $$n > 1$$ there is a unique expression for $$n$$,

$$
n=p_1^{k_1}p_2^{k2}\cdots p_r^{k_r},
$$

where $$p_1 < p_2 < \cdots < p_r$$ are [prime numbers](https://en.wikipedia.org/wiki/Prime_number). We have

$$
\Phi(n)=n\Big(1-\frac{1}{p_1}\Big)\Big(1-\frac{1}{p_2}\Big)\cdots \Big(1-\frac{1}{p_r}\Big)
$$

## Examples

$$15=3\times5\Rightarrow\Phi(12)=(3-1)(5-1)=8$$

$$\Phi(12)=\Phi(3^14^1)=12\Big(1-\frac{1}{3}\Big)\Big(1-\frac{1}{4}\Big)=12\cdot\frac{2}{3}\cdot\frac{3}{4}=6$$

