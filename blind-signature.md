# Blind Signature

**Blind signature** is a form of digital signature in which the content of a message is disguised \(blinded\) before it is signed.

Blind signatures are typically employed in privacy-related protocols where the signer and message author are different parties. Examples include cryptographic election systems and [digital cash](https://en.wikipedia.org/wiki/Digital_cash) schemes.

## Blind RSA signature

1. The author of the message computes the product of the message $$m$$ and blinding factor $$r$$, i.e.: $$m'\equiv mr^e\pmod N$$, where $$(e,N)$$is the signing authority's RSA public key.
2. The signing authority then calculates the blinded signature $$s'$$ as: $$s'\equiv (m')^d\pmod N$$.
3. The signing authority sends $$s'$$back to the author of the message.
4. The author of the message can then remove the blinding factor to reveal $$s$$, the valid signature of $$m$$: $$s\equiv s'\cdot r^{-1}\pmod N$$.

## Proof

$$r^{ed}\equiv r{\pmod {N}}$$

$$s\equiv s'\cdot r^{-1}\equiv (m')^{d}r^{-1}\equiv m^{d}r^{ed}r^{-1}\equiv m^{d}rr^{-1}\equiv m^{d}{\pmod {N}}$$

