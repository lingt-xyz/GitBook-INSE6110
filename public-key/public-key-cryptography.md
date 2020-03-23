# Public key cryptography

## What it is

* **Each party** has a pair $$(P, S)$$ of keys: $$P$$ is the public key and $$S$$ is the secret key. 
* Knowing the public-key and the cipher, it is still computationally infeasible to compute the private key \(an NP-class problem\).
* The public-key may be distributed to anyone wishing to communicate securely with its owner.

## Trapdoor One-way Functions

A function $$f: \{0,1\}^* \rightarrow \{0,1\}$$ __ is a trapdoor one-way function iff $$f(x)$$ is a one-way function; however, given some extra information it becomes feasible to compute $$f^{-1}$$.

Public key cryptography relies on trapdoor one-way functions.

