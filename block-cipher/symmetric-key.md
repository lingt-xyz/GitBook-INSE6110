# Symmetric Key

## Symmetric Key Cryptosystem

### Advantages

* high data throughput
* relatively short size 

### Disadvantages

* the key must remain secret at both ends.
* $$O(n^2)$$ keys to be managed.

## Symmetric-key Ciphers

### Block ciphers

* process plaintext in relatively large blocks\(e.g. $$n>64$$bits\)
* The same function is used to encrypt successive blocks, so memory less

### Stream ciphers

* process plaintext in small blocks, and the encryption function may vary as plaintext is processed, so need memory
* sometimes called state ciphers since encryption depends on not only the key and plaintext, but also on the current state.

## Block Ciphers

Design Parameters

* Block size
* Key size
* Structure \(Feistel and SPNs\)

