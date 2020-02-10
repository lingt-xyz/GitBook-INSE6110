# Project

## [A Fast Method for the Cryptanalysis of Substitution Ciphers](https://moodle.concordia.ca/moodle/pluginfile.php/3909361/mod_resource/content/0/A%20Fast%20Method%20for%20the%20Cryptanalysis%20of%20Substitution%20Ciphers.pdf)

A **mono-alphabetic** substitution cipher is a cipher where a one-to-one mapping is used to substitute each plaintext symbol with a corresponding ciphertext symbol.

In a **polyalphabetic** cipher more than one such mapping is used.

### Algorithm 

* Used for ciphertext-only attacks.
* Used for monoalphabetic cipher.

The algorithm starts by making an initial guess about what the key is. This guess 

* can be made on basis of a simple analysis of the ciphertext, 
* it can be based on partial knowledge of the key or 
* it can be purely random.

The resulting text will have a certain similarity to the expected language of the plaintext depending on how many correct symbols there were in the guess in the first place.

In the iterated loop which follows we first alter the current key a little bit, then this key is used to decrypt the ciphertext once again and finally we check if the contents of the new resulting text are closer to the expected language than those of the previously decrypted text. If they are, we keep the new key for the next iteration, if not the old one is used but modified in another way next time the loop is run through etc.

a function which reflects "how close" the contents of a given text are to the expected language.

## [Efficient Cryptanalysis of Homophonic Substitution Ciphers](https://moodle.concordia.ca/moodle/pluginfile.php/3909362/mod_resource/content/0/Substitution%20ciphers.pdf)

A simple substitution is a one-to-one mapping in the sense that each plaintext symbol corresponds to one ciphertext symbol.

Homophonic substitutions—in which a plaintext symbol can map to more than one ciphertext symbol

