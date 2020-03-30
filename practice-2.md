# Practice 2

## Q1

Suppose that users Alice and Bob carry out the Diffie-Hellman key agreement protocol with $$p = 101$$ and $$g = 17$$. Suppose that Alice chooses $$x = 19$$ and Bob chooses $$y = 13$$. Show the computations performed by both Alice and Bob, and determine the key that they will share.

$$17^{1}\mod 101 =17$$

$$17^{2}\mod 101 =87$$

$$17^{4}\mod 101 =95$$

$$17^{8}\mod 101 =36$$

$$17^{16}\mod 101 =84$$

Alice to Bob: $$g^{x_a}\mod p\equiv 17^{19}\mod 101=(84\times 87\times 17)\mod 101=6$$

Bob to Alice: $$g^{x_b}\mod p\equiv 17^{13}\mod 101=(36\times 95\times17)\mod 101=65$$

$$6^{1}\mod 101 =6$$

$$6^{2}\mod 101 =36$$

$$6^{4}\mod 101 =84$$

$$6^{8}\mod 101 =87$$

Shared key: $$K_{x_{ab}}=g^{x_ax_b}\mod p\equiv 6^{13}\mod 101\equiv 65^{19}\mod 101=14$$

## Q2

Suppose that users Alice and Bob carry out the 3-pass Diffie-Hellman protocol with $$p = 101$$. Suppose that Alice chooses $$a_1 = 19$$ and Bob chooses $$b_1 = 13$$. If Alice wants to send the secret message $$m=5$$ to Bob, show all the messages exchanged between Alice and Bob.

Alice computes $$a_2={a_1}^{-1}\mod (p-1)=79$$

Bob computes $$b_2={b_1}^{-1}\mod (p-1)=77$$

Alice to Bob $$c_1 = m^{a_1}\mod p=37$$

Bob to Alice $$c_2={c_1}^{b_1}\mod p = m^{a_1b_1}\mod p=80$$

Alice to Bob $$c_3={c_2}^{a_2}\mod p = m^{a_1b_1a_2}\mod p=56$$

Bob decrypts $$m={c_4}^{b^2}\mod p=m^{a_1b_1a_2b_2}\mod p=m\mod p=m=5$$

## Q3

Consider an RSA system with $$p=7, q=11$$ and $$e=13$$. Find the plaintext corresponding to $$c=17$$.

Compute $$N=pq=7\times11=77$$

Compute $$\Phi(N)=(p-1)(q-1)=6\times10=60$$

Compute $$d=e^{-1}\bmod\Phi(N)={13}^{-1}\bmod 60=-23\bmod 60=37$$

| $$R_i$$ | $$D_i$$ | $$S_i$$ |
| :--- | :--- | :--- |
| 60 |  | 0 |
| 13 | 4 | 1 |
| 8 | 1 | $$0-1\times4=-4$$ |
| 5 | 1 | $$1-(-4\times1)=5$$ |
| 3 | 1 | $$-4-5\times1=-9$$ |
| 2 | 1 | $$5-(-9\times1)=14$$ |
| 1 |  | $$-9-14\times1=-23$$ |

Decrypt $$m=c^d\mod N=17^{37}\mod 77$$

Speed up decryption by CRT.

$$\begin{align}m_p&=17^{37}\mod 7\equiv 17^1\mod 7\equiv 3^1\mod 7=3\\m_q&=17^{37}\mod 11\equiv 17^7\mod 11\equiv 6^7\mod 11=8\end{align}$$

$$x\equiv 3\bmod7, x\equiv 8\bmod11$$

$$3\times 11\times (11^{-1}\bmod 7)+8\times7\times(7^{-1}\bmod 11)=52$$

## Q4: Common $$p$$ Attack

Consider an RSA system in which the attacker knows that $$n_1$$ and $$n_2$$ has the form $$n_1=pq_1=16637 $$and $$n_2=pq_2=17399$$. Show how the attacker can break this system.

$$gcd(n_1,n_2)=127\Rightarrow p=127,q_1=131,q_2=137$$

$$e$$is public, $$n_1,n_2$$are known, then $$d_1,d_2$$ can be computed.

## Q5: Common Modulus Attack

Consider an RSA system with $$N=143, e_1=7$$ and $$e_2=17$$. Suppose the same message $$m$$ was sent to the two users above and the attacker observed the ciphertext $$c_1=42$$ and $$c_2=9$$. Show how the attacker can recover the message.

Check $$gcd(e_1,e_2)=1$$

| $$R_i$$ | $$D_i$$ | $$S_i$$ |
| :--- | :--- | :--- |
| 17 |  | 0 |
| 7 | 2 | 1 |
| 3 | 2 | $$0-1\times2=-2$$ |
| 1 |  | $$1-(-2)\times2=5$$ |

$$a_1e_1\times a_2e_2=5\times7-2\times17=1\Rightarrow a_1=5,a_2=-2$$

$$\begin{align}m&=c_1^{a_1}\times c_2^{a_2}\mod N\\&=42^5\times 9^{-2}\mod 143\\&=100\times 81^{-1}\mod 143\\&=100\times 113\mod 143\\&=3\end{align}$$

Check $$3^7\mod 143=42, 3^{17}\mod 143=9$$

## Q6: Twin Prime Attach

Consider an RSA that is using twin primes. If $$n=10403$$ and $$e=8743$$. Show how the adversary can recover the message corresponding to $$c=99$$.

$$p(p+2)=10403\Rightarrow p=101, q=103\Rightarrow\Phi(N)=10200\Rightarrow d=e^{-1}\mod \Phi(N)=7$$

$$m=c^d\mod N=99^{7}\mod (101\times103)=9366$$

## Q7: **Low Exponent Attack**

Consider an RSA system where the public key of three users \(i.e., $$(n,e)$$\) are given by: $$(319,3), (697,3)$$ and $$(1081,3)$$. If the same message was sent to the three users. Show how the attacker can recover $$m$$ by observing the ciphertexts $$c_1=128, c_2=34$$ and $$c_3=589$$.

$$c\equiv m^e\mod N\Rightarrow c\equiv m^3\mod N\Rightarrow m^3=c\mod N$$

The attacker uses the CRT to solve for $$m^3\mod (n_1 n_2 n_3)$$. Just denote $$m^3$$ by $$x$$. Then this is equivalent to solving for $$x$$ that satisfies:

$$\begin{cases} x=128 \mod 319 \\  x=34 \mod 697 \\  x=589 \mod 1081 \end{cases}$$

Using CRT we get $$x=4913\Rightarrow m=4913^{1/3}=17$$.

