# Diffie-Hellman

## Deffie-Hellman three passes

### Algorithm

* $$p$$: a large prime integer, public
* $$a_1$$: Alice's private key
* $$a_2$$: $$a_2\equiv {a_1}^{-1}\pmod {p-1}$$
* $$b_1$$: Bob's private key
* $$b_2$$: $$b_2\equiv {b_1}^{-1}\pmod {p-1}$$
* $$m$$: message to be passed between Alice and Bob

### Entryption: Three passes

* Pass 1: Alice to Bob
  * $$m^{a_1}\pmod p$$
* Pass 2: Bob to Alice
  * $$(m^{a_1}\pmod p)^{b_1}\pmod p\equiv m^{a_1b_1}\pmod p$$
* Pass 3: Alice to Bob
  * $$(m^{a_1b_1}\pmod p)^{a_2}\pmod p\equiv m^{a_1b_1a_2}\pmod p$$

### Decryption

$$(m^{a_1b_1a_2}\pmod p)^{b_2}\pmod p\equiv m^{a_1b_1a_2b_2}\pmod p\equiv m$$

## Algorithm

* $$p$$, a large prime integer, public
* $$g$$, a primitive root mod p, public \(also called a generator\)
* Session key is then obtained by both parties calculating:
  * a,ba,b are private to Alice and Bob respectively
  * Kab=gab\(modp\)Kab=gab\(modp\)
  * Alice can compute Kab=gba\(modp\)Kab=gba\(modp\)
  * Bob can compute Kab=gab\(modp\)Kab=gab\(modp\)
* {Message,Password}k



