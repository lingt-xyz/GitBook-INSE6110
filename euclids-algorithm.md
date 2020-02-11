# Euclid's algorithm

[Euclidean algorithm](https://en.wikipedia.org/wiki/Euclidean_algorithm) uses a [division algorithm](https://en.wikipedia.org/wiki/Division_algorithm) such as [long division](https://en.wikipedia.org/wiki/Long_division) in combination with the observation that the $$gcd$$ of two numbers also divides their difference. To compute $$gcd(48,18)$$, divide 48 by 18 to get a quotient of 2 and a remainder of 12. Then divide 18 by 12 to get a quotient of 1 and a remainder of 6. Then divide 12 by 6 to get a remainder of 0, which means that 6 is the gcd. We ignored the quotient in each step except to notice when the remainder reached 0, signalling that we had arrived at the answer. Formally the algorithm can be described as

$$
\begin{align}
gcd(a,0)&=a\\
gcd(a,b)&=gcd(b, a\bmod b)
\end{align}
$$

Examples see [Practice 1](https://inse6110.lingt.xyz/practice-1).

