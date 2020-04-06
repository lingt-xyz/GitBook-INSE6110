---
description: Message Authentication Code
---

# MAC

## Message Authentication Code

* Keyed hash functions are called MACs, which use both $$m$$ and a key $$k$$ as input.
* Why need it
  * Encryption alone does not provide data integrity.
* Goal
  * add authentication to the hash-value by using a secret \(symmetric\) key.
* Properties
  * Should be difficult to create a valid MAC without knowledge of secret key

## Algorithm

* $$m$$: message
* $$k$$: private key
* $$h_k$$: hash function using the private key $$k$$

### Encryption

Sender sends $$m$$and $$h_k(m)$$.

## CBC MAC

## Authentication Protocol

