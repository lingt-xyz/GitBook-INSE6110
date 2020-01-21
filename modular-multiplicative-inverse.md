# Modular multiplicative inverse

## Definition

A **modular multiplicative inverse** of an integer $$\alpha$$ is an integer $$x$$ such that

$$
ax \equiv 1 \pmod{m}
$$

That is

$$
x\equiv a^{-1}\pmod{m}
$$

## Algorithm

* $$R_i$$is the reminder.
* $$S_i=S_{i-2}-S_{i-1}\times D_{i-1}$$

### Examples

### $$3^{-1}\pmod{26}$$

| $$R_i$$ | $$D_i$$ |  | $$S_i$$ |
| :--- | :--- | :--- | :--- |
| 26 |  |  | 0 |
| 3 | 8 | $$26/3=8,26\%3=2$$ | 1 |
| 2 | 1 | $$3/2=1,3\%2=1$$ | $$0-1\times8=-8$$ |
| 1 |  |  | $$1-(-8)\times 1=9$$ |

$$9\pmod{26}\equiv 9\equiv 3^{-1}\pmod{26}$$

### $$7^{-1}\pmod{26}$$

| $$R_i$$ | $$D_i$$ |  | $$S_i$$ |
| :--- | :--- | :--- | :--- |
| 26 |  |  | 0 |
| 7 | 3 | $$7\times3+5=26$$ | 1 |
| 5 | 1 | $$5\times1+2=7$$ | $$0-1\times3=-3$$ |
| 2 | 2 | $$2\times2+1=5$$ | $$1-(-3)\times 1=4$$ |
| 1 |  |  | $$(-3)-(4)\times(2)=-11$$ |

$$-11\pmod{26}=15=7^{-1}$$

