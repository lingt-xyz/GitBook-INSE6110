# ElGamal Signature

## Key Generation

As in ElGamal encryption:

* $$p$$: a large prime integer; _**public**_.
* $$g$$: a primitive root mod $$p$$\(also called a generator\); _**public**_.
* $$a$$: choose an integer $$a$$randomly from $$\{1,2,\dots,p-2\}$$; _**private**_.
* $$y$$: compute $$y=g^a\pmod p$$; _**public**_.

## Signing

A message $$m$$ is signed as follows:

* Choose an integer $$k$$ randomly from $$\{1,2,\ldots, p-1\}$$ with $$k$$ relatively prime to $$p-1$$.
* Compute $$r=g^{k}{\pmod {p}}$$.
* Compute $$s=k^{-1}(m-ar){\pmod {p-1}}$$.
* In the unlikely event that $$s=0$$ start again with a different random $$k$$.

The signature is $$(r,s)$$.

## Verifying

One can verify that a signature $$(r,s)$$ is a valid signature for a message $$m$$ as follows:

* The signature is valid if and only if $$g^m\equiv y^{r}r^{s}{\pmod {p}}$$.

## Correctness

The computation of $$s$$ during signature generation implies $$m\equiv sk+ar{\pmod {p-1}}$$.

Hence [Fermat's little theorem](https://inse6110.lingt.xyz/fermats-little-theorem) implies

$$
\begin{aligned}g^{m}&\equiv g^{xr}g^{ks}\\&\equiv (g^{x})^{r}(g^{k})^{s}\\&\equiv (y)^{r}(r)^{s}{\pmod {p}}.\\\end{aligned}
$$

