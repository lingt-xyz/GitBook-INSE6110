# Secret Sharing

## Problem Statement

Given a secret, $$s$$, would like $$n$$ parties to share the secret so that the following properties hold:

1. All $$n$$ parties can get together and recover $$s$$.
2. Less than $$n$$ parties cannot recover $$s$$.

## Protocol Secret Splitting

\($$n$$out of $$n$$scheme\)

1. Given a secret, $$M$$ of length $$n$$ .
2. Given $$N$$ persons who will share the secret \(named $$p_1, p_2, \cdots, p_N$$\) .
3. Generate random bit strings $$R_1,R_2,\cdots, R_{N-1}$$ or length.
4. Calculate $$P = M \text{ xor } R_1\text{ xor }R_2\cdots \text{ xor }R_{N_1}$$.
5. Destroy or hide $$M$$.
6. Give $$P$$ to $$p_1$$, give $$R_{1}$$ to $$p_2$$, ..., give $$R_{N-1}$$ to $$p_N$$.

### Problem

Vulnerable to the loss of one site. If one person lost the key, then $$M$$cannot be revealed.

## Shamir Secret Sharing Scheme

\($$m$$out of $$n$$scheme\)

A secret is divided into $$n$$ pieces \(called the shadows\), such that combining any $$m$$ of the shadows will reconstruct the original secret.

1. Choose a \(public\) large polynomial $$p$$ bigger than
   1. the possible number of shadows
   2. the size of the secret
   3. other requirements for strength
   4. all arithmetic will be $$\pmod p$$
2. Generate an arbitrary polynomial of degree $$m-1$$.
3. Evaluate the polynomial at $$n$$ different points to obtain the shadows $$k_i$$.
4. Distribute the shadows and destroy $$M$$ and all the polynomial coefficients.

### e.g.

$$(n,3)$$ Threshold scheme

$$m=3$$so polynomial is degree $$2$$; $$F(x)=(ax^2+bx+M) \mod M$$

## Sharing Secret with Cheaters

Hash shadows.

