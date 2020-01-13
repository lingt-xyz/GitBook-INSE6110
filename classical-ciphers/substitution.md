# Substitution

## Substitution

In a substitution cipher, letters of plaintext are replaced by other letters or numbers or symbols.

* No punctuations.
* No differentiation between capital and lowercase letters.

{% hint style="info" %}
Why? To reduce information exposure.

e.g.: If there is a capital letter, this could mean this letter is a beginning of a sentence.
{% endhint %}

### Algorithm

Define plaintext space and cipher space over $$Z_{26}$$:

| A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 | 22 | 23 | 24 | 25 |

Let $$P = C = Z_{26}$$.

Define $$K$$where $$0 ≤ K ≤ 25$$.

* $$e_K(P) = (P + K) \pmod {26}$$ 
* $$d_K(C) = (C - K) \pmod {26}$$

## No shifting

$$K=0$$

* Letters of plaintext are replaced by other letters or numbers or symbols.

## Caesar Cipher

$$K=3$$

* $$e_K(P) = (P + 3) \pmod {26}$$ 
* $$d_K(C) = (C - 3) \pmod {26}$$

## Shift Cipher

Define $$K$$where $$0 ≤ K ≤ 25$$.

* $$e_K(P) = (P + K) \pmod {26}$$
* $$d_K(C) = (C - K) \pmod {26}$$

### Cryptanalysis

exhaustive search: 26 possible keys.

