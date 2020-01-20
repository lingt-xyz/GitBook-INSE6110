# Stream Cipher

This page covers some classical stream ciphers, which are also broadly categorized to substitution cipher.

In a substitution\(stream\) cipher, letters of plaintext are replaced by other letters or numbers or symbols.

* No punctuations.
* No differentiation between capital and lowercase letters.

{% hint style="info" %}
Why? To reduce information exposure.

e.g.: If there is a capital letter, this could mean this letter is a beginning of a sentence.
{% endhint %}

## Algorithm

Define plaintext space and cipher space over $$\Bbb{Z}_{26}$$:

| A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 | 22 | 23 | 24 | 25 |

Let $$P = C = \Bbb{Z}_{26}$$.

## No shifting

* Letters of plaintext are replaced by other letters or numbers or symbols.

## Caesar Cipher

* $$e_K(P) = (P + 3) \pmod {26}$$ 
* $$d_K(C) = (C - 3) \pmod {26}$$

## Shift Cipher

Define $$K$$where $$0 ≤ K ≤ 25$$.

* $$e_K(P) = (P + K) \pmod {26}$$
* $$d_K(C) = (C - K) \pmod {26}$$

### Cryptanalysis

* Key space: $$26$$
* Exhaustive search $$26$$ possible keys.

## Substitution Ciphers

Substitute a plaintext with another plaintext. E.g.: substitute $$A$$with $$B$$, substitute $$B$$with $$E$$, and continue on.

* $$e_{\Pi}(P)=\Pi(P)$$
* $$d_{\Pi}(C)={\Pi}^{-1}(C)$$

### Cryptanalysis

* Key space: $$26!\approx2^{88}$$
* Exhaustive search is infeasible.

Substitution ciphers preserve language statistics.

* Frequency analysis attacks

## Affine cipher

* $$e_K(X)=Y=(\alpha X +\beta)\pmod {26}$$
* $$d_K(Y)=X={\alpha}^{-1}(Y-\beta)\pmod{26}$$
* $$K=(\alpha,\beta), \text{ and }\alpha,\beta\in \Bbb{Z}_{26}$$

### Valid Key Space

* $$\beta$$can be any number in $$\Bbb{Z}_{26}$$, so there are$$26$$possibilities.
* Since $$\alpha^{-1}$$has to exist, only integer in $$\Bbb{Z}^{26}$$such that $$gcd(\alpha,26)=1$$can be selected.
  * The candidates are $$\{1,3,5,7,9,11,15,17,19,21,23,25\}$$.
* Key space: $$26\times12=312$$
* To calculate $$\alpha^{-1}$$, see [Modular Inverse](https://inse6110.lingt.xyz/modular-inverse).

### Cryptanalysis

#### Ciphertext only

exhaustive search or frequency analysis.

#### Known plaintext

two letters in the plaintext and corresponding ciphertext letters would suffice to find the key.

Because there are only two variables: $$\alpha,\beta$$

#### Chosen plaintext

Choose$$A=0$$and$$B=1$$.

The first character of the ciphertext will be equal to $$0\cdot \alpha + \beta = \beta$$ and the second will be $$\alpha + \beta$$.

