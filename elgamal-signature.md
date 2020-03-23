# ElGamal Signature

## Key Generation

As in ElGamal encryption:

* $$p$$: a large prime integer; public.
* $$g$$: a primitive root mod $$p$$\(also called a generator\); public.
* $$x$$: choose an integer $$x$$randomly from $$\{1,2,\dots,p-2\}$$; private.
* $$y$$: compute $$y=g^x\pmod p$$; public.

## Signing

A message $$m$$ is signed as follows:

* Choose an integer $$k$$ randomly from $$\{2\ldots p-2\}$$ with $$k$$ relatively prime to $$p-1$$.
* Compute $$r:=g^{k}{\pmod {p}}$$.
* Compute $$s:=(h(m)-xr)k^{-1}{\pmod {p-1}}$$.
* In the unlikely event that $$s=0$$ start again with a different random $$k$$.

The signature is $$(r,s)$$.

## Verifying

One can verify that a signature $$(r,s)$$ is a valid signature for a message $$m$$ as follows:

* The signature is valid if and only if $$g^{h(m)}\equiv y^{r}r^{s}{\pmod {p}}$$.

## Correctness

The computation of $$s$$ during signature generation implies $$h(m)\,\equiv \,xr+sk{\pmod {p-1}}$$.

Hence [Fermat's little theorem](https://inse6110.lingt.xyz/fermats-little-theorem) implies

$$
\begin{aligned}g^{h(m)}&\equiv g^{xr}g^{ks}\\&\equiv (g^{x})^{r}(g^{k})^{s}\\&\equiv (y)^{r}(r)^{s}{\pmod {p}}.\\\end{aligned}
$$

