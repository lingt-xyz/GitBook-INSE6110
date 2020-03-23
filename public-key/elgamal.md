# ElGamal Encryption

Its security based on the intractability of the **discrete logarithm problem**.

Message expansion: the ciphertext is twice as big as the original message.

Uses randomization, each message has $$p-1$$ possible different encryptions.

## Key generation

The first party, Alice, generates a key pair as follows:

* $$p$$: a large prime integer; public.
* $$g$$: a primitive root mod $$p$$\(also called a generator\); public.
* $$x$$: choose an integer $$x$$randomly from $$\{1,2,\dots,q-1\}$$; private.
* $$h$$: compute $$h=g^x$$; public.

## Encryption

1. Choose an integer $$y$$randomly from $$\{1,2,\dots,q-1\}$$.
2. Compute $$s =h^y$$. This is called the shared secret.
3. Compute $$c_1=g^y$$
4. Compute $$c_2=m\cdot s$$
5. Bob sends the ciphertext $$(c_1, c_2)$$to Alice.

## Decryption

Alice decrypts a ciphertext $$(c_{1},c_{2})$$with her private key $$x$$ as follows:

1. Compute $$s=c_1^x$$. Since$$c_{1}=g^{y}$$, $$c_{1}^{x}=g^{xy}=h^{y}$$ and thus it is the same shared secret that was used by Bob in encryption.
2. Compute $$s^{-1}$$.
3. Compute $$m=c_2\cdot s^{-1}$$. This calculation produces the original message $$m$$, because $$c_{2}=m\cdot s$$; hence $$c_{2}\cdot s^{-1}=(m\cdot s)\cdot s^{-1}=m\cdot e=m$$.

