# Block Cipher

## Hill Cipher

Hill Cipher is a type of block cipher. Its key is a matrix$$M$$.

{% hint style="info" %}
If we change one letter in the plaintext, all the letters of the ciphertext will be affected.
{% endhint %}

In order to decrypt we need the inverse of key matrix $$M$$.

### Properties

1. Diffusion: one character change in the plaintext should effect as many ciphertext characters as possible, and vice versa.
2. Confusion: The key/plaintext should not relate to the ciphertext in a simple way.

### Example

## One Time Pad

### Algorithm

* $$X = Y = K = (\mathbb{Z}m)^n$$ 
* $$X = (x_1\ x_2\ \cdots\ x_n)$$
* $$K = (k_1\ k_2\ \cdots\ k_n)$$
* $$Y = (y_1\ y_2\ \cdots\  y_n)$$ 
* $$e_K(X) = (x_1+k_1\ x_2+k_2\ \cdots\ x_n+k_n) \mod m$$ 
* $$d_k(Y) = (y_1-k_1\ y_2-k_2\ \cdots\ y_n-k_n) \mod m$$

### Provable security 

The security depends on the randomness of the key:

* Unpredictability: Independent of the number of the bits of a sequence observed, the probability of guessing the next bit is not better than ½. Therefore, the probability of a certain bit being 1 or 0 is exactly equal to ½. 
* Balanced \(Equal Distribution\): The number of 1’s and 0’s should be equal.

Mathematical Proof

* The probability of a key bit being 1 or 0 is exactly equal to ½. 
* The plaintext bits are not balanced. Let the probability of 0 be$$x$$ and then the probability of 1 turns out to be$$1-x$$.

| $$m_i$$ |  prob. | $$k_i$$ |  prob. | $$c_i$$  | prob. |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 0 | $$x$$ | 0   | ½ | 0  | ½$$x$$ |
| 0 | $$x$$ | 1 | ½ | 1 | ½$$x$$ |
| 1 | $$1-x$$ | 0 | ½ | 1 | ½$$(1-x)$$ |
| 1 | $$1-x$$ | 1 | ½ | 0 | ½$$(1-x)$$ |

$$
p(c_i=0)=1/2x+1/2(1-x)=1/2\\
p(c_i=1)=1/2x+1/2(1-x)=1/2
$$

### Disadvantages

* The size of key must be at least the size of the message
* Each key is used only once. Otherwise, vulnerable to know plaintext attack.

