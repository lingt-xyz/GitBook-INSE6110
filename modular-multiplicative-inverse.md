# Modular multiplicative inverse

## Definition

A **modular multiplicative inverse** of an integer $$\alpha$$ with respect to the modulus $$N$$ is an integer $$x$$ such that

$$
\alpha x \equiv 1 \pmod{N}
$$

That is

$$
x\equiv \alpha^{-1}\pmod{N}
$$

To be able have a solution, $$gcd(\alpha,N)=1$$.

## Algorithm

1. Verify that $$gcd(\alpha,N)=1$$.
2. Caculate the multiplicative inverse by the following approch.
   * $$R_i$$is the reminder.
   * $$S_i=S_{i-2}-S_{i-1}\times D_{i-1}, \text{ for }i\geq2$$
   * $$S_0=0,S_1=1$$

## Examples

### Example 1

$$3^{-1}\pmod{26}$$

| $$R_i$$ | $$D_i$$ |  | $$S_i$$ |
| :--- | :--- | :--- | :--- |
| 26 |  |  | 0 |
| 3 | 8 | $$26/3=8,26\%3=2$$ | 1 |
| 2 | 1 | $$3/2=1,3\%2=1$$ | $$0-1\times8=-8$$ |
| 1 |  |  | $$1-(-8)\times 1=9$$ |

The last $$R_i$$is $$1$$, that means $$gcd(3,26)=1$$.

$$9\pmod{26}\equiv 9\equiv 3^{-1}\pmod{26}$$

### Example 2

$$7^{-1}\pmod{26}$$

| $$R_i$$ | $$D_i$$ |  | $$S_i$$ |
| :--- | :--- | :--- | :--- |
| 26 |  |  | 0 |
| 7 | 3 | $$26/7=3,26\%7=5$$ | 1 |
| 5 | 1 | $$7/5=1,7\%5=2$$ | $$0-1\times3=-3$$ |
| 2 | 2 | $$5/2=2,5\%2=1$$ | $$1-(-3)\times 1=4$$ |
| 1 |  |  | $$(-3)-(4)\times(2)=-11$$ |

The last $$R_i$$is $$1$$, that means $$gcd(7,26)=1$$.

$$-11\pmod{26}\equiv15\equiv7^{-1}\pmod{26}$$

### Example 3

$${121}^{-1}\pmod{803}$$

| $$R_i$$ | $$D_i$$ |
| :--- | :--- |
| 803 |  |
| 121 | 6 |
| 77 | 1 |
| 44 | 1 |
| 33 | 1 |
| 11 | 3 |
| 0 |  |

$$gcd(121,803)=11\neq1$$, so there is no solution.

### Example 4

$${160}^{-1}\pmod{841}$$

| $$R_i$$ | $$D_i$$ | $$S_i$$ |
| :--- | :--- | :--- |
| 841 |  | 0 |
| 160 | 5 | 1 |
| 41 | 3 | $$0-1\times5=-5$$ |
| 37 | 1 | $$1-(-5)\times3=16$$ |
| 4 | 9 | $$-5-16\times1=-21$$ |
| 1 |  | $$16-(-21\times9)=205$$ |

The last $$R_i$$is $$1$$, that means $$gcd(160,841)=1$$.

$$205\pmod{841}\equiv205\equiv{160}^{-1}\pmod{841}$$

### More Examples

* $$14\equiv 5^{-1}\pmod{23}$$
* $$67\equiv {111}^{-1}\pmod{143}$$



