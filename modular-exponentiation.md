---
description: Square and multiply
---

# Modular exponentiation

## Statement

Given $$c=a\cdot b$$,

$$
c\bmod m=(a\times b)\bmod m=\big[(a\bmod m)\cdot(b\bmod m)\big]\bmod m
$$

## Examples

### Example 1

$$7^6\pmod{11}=({7^2\times 7^4})\pmod{11}$$

$$7^2\pmod{11}\equiv5\\ \Rightarrow 7^4\pmod{11}=(5\times 5)\pmod {11}=25\pmod{11}\equiv3\\ \Rightarrow7^6\pmod{11}=(5\times3)\pmod{11}=15\pmod{11}\equiv4$$



