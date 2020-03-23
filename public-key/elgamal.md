# ElGamal Encryption

Its security based on the intractability of the **discrete logarithm problem**.

Message expansion: the ciphertext is twice as big as the original message.

Uses randomization, each message has $$p-1$$ possible different encryptions.

## Algorithm

* $$p$$, a large prime integer
* $$g$$, a primitive root mod $$p$$\(also called a generator\)
* Public key is $$y=g^k$$, private key is $$k$$

## Encryption

1. Generate random integer $$k$$ and compute $$r = g^k \pmod p$$
2. Compute $$c = m y^k \pmod p$$
3. Ciphertext \(r, c\)

## Decryption

$$m = c r^{ –a} \pmod p$$

