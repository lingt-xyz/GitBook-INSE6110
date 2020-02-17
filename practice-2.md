# Practice 2

## Q1

Suppose that users Alice and Bob carry out the Diffie-Hellman key agreement protocol with $$p = 101$$ and $$g = 17$$. Suppose that Alice chooses $$x = 19$$ and Bob chooses $$y = 13$$. Show the computations performed by both Alice and Bob, and determine the key that they will share.

Alice to Bob: $$g^{x_a}\mod p\equiv 17^{19}\mod 101=$$

Bob to Alice: $$g^{x_b}\mod p\equiv 17^{13}\mod 101=$$

Shared key: $$K_{x_{ab}}=g^{x_ax_b}\mod p\equiv17^{19\times13}\mod101=$$

## Q2

Suppose that users Alice and Bob carry out the 3-pass Diffie-Hellman protocol with $$p = 101$$. Suppose that Alice chooses $$a_1 = 19$$ and Bob chooses $$b_1 = 13$$. If Alice wants to send the secret message $$m=5$$ to Bob, show all the messages exchanged between Alice and Bob.

Alice computes $$a_2={a_1}^{-1}\mod (p-1)=$$

Bob computes $$b_2={b_1}^{-1}\mod (p-1)=$$

Alice to Bob $$c_1 = m^{a_1}\mod p=$$

Bob to Alice $$c_2={c_1}^{b_1}\mod p = m^{a_1b_1}\mod p=$$

Alice to Bob $$c_3={c_2}^{a_2}\mod p = m^{a_1b_1a_2}\mod p=$$

Bob decrypts $$m={c_4}^{b^2}\mod p=m^{a_1b_1a_2b_2}\mod p=m\mod p=m$$

## Q3

Consider an RSA system with $$p=7, q=11$$ and $$e=13$$. Find the plaintext corresponding to $$c=17$$.

Compute $$N=pq=$$

Compute $$\Phi(N)=(p-1)(q-1)=$$

Compute $$d=e^{-1}\mod\Phi(N)=$$

Encrypt $$m=c^e\mod N=$$

## Q4

Consider an RSA system in which the attacker knows that $$n_1$$ and $$n_2$$ has the form $$n_1=pq_1=16637 $$and $$n_2=pq_2=17399$$. Show how the attacker can break this system.

$$gcd(n_1,n_2)=127\Rightarrow p=127,q_1=131,q_2=137$$

## Q5

Consider an RSA system with $$N=143, e_1=7$$ and $$e_2=17$$. Suppose the same message $$m$$ was sent to the two users above and the attacker observed the ciphertext $$c_1=42$$ and $$c_2=9$$. Show how the attacker can recover the message.

Check $$gcd(e_1,e_2)=1$$

| $$R_i$$ | $$D_i$$ | $$S_i$$ |
| :--- | :--- | :--- |
| 17 |  | 0 |
| 7 | 2 | 1 |
| 3 | 2 | $$0-1\times2=-2$$ |
| 1 |  | $$1-(-2)\times2=5$$ |

$$5\times7-2\times17=1\Rightarrow a_1=5,a_2=-2$$

$$\begin{align}m&=c_1^{a_1}\times c_2^{a_2}\mod N\\&=42^5\times 9^{-2}\mod 143\\&=100\times 81^{-1}\mod 143\\&=100\times 113\mod 143\\&=3\end{align}$$

Check $$c^7\mod 143=42, 3^{17}\mod 143=9$$

## Q6

Consider an RSA that is using twin primes. If $$n=10403$$ and $$e=8743$$. Show how the adversary can recover the message corresponding to $$c=99$$.

## Q7

Consider an RSA system where the public key of three users \(i.e., $$(n,e)$$ are given by: $$(319,3), (697,3)$$ and $$(1081,3)$$. If the same message was sent to the three users. Show how the attacker can recover $$m$$ by observing the ciphertexts $$c_1=128, c_2=34$$ and $$c_3=589$$.

