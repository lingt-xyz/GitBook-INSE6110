# Euler's criterion

## Formula

In number theory, **Euler's criterion** is a formula for determining whether an integer is a [quadratic residue](https://en.wikipedia.org/wiki/Quadratic_residue) [modulo](https://en.wikipedia.org/wiki/Modular_arithmetic) a prime. Precisely,

Let p be an odd prime and a be an integer [coprime](https://en.wikipedia.org/wiki/Coprime) to p. Then

$$
a^{\tfrac {p-1}{2}}\equiv {\begin{cases}
\;\;\,1{\pmod {p}}&{\text{ if there is an integer }}x{\text{ such that }}a\equiv x^{2}{\pmod {p}}\\-1{\pmod {p}}&{\text{ if there is no such integer.}}
\end{cases}}
$$

Euler's criterion can be concisely reformulated using the [Legendre symbol](https://en.wikipedia.org/wiki/Legendre_symbol):

$$
\left({\frac {a}{p}}\right)\equiv a^{\tfrac {p-1}{2}}{\pmod {p}}
$$

## Proof

As a is coprime to p, [Fermat's little theorem](https://en.wikipedia.org/wiki/Fermat%27s_little_theorem) says that

$$
a^{p-1}\equiv 1{\pmod {p}}
$$

which can be written as

$$
\left(a^{\tfrac {p-1}{2}}-1\right)\left(a^{\tfrac {p-1}{2}}+1\right)\equiv 0{\pmod {p}}
$$

Since the integers mod $$p$$ form a field, for each $$a$$, one or the other of these factors must be zero.

Now if $$a$$ is a quadratic residue, $$a \equiv x^2$$,

$$
a^{\tfrac {p-1}{2}}\equiv {(x^{2})}^{\tfrac {p-1}{2}}\equiv x^{p-1}\equiv 1{\pmod {p}}
$$

