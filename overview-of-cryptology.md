# Overview of Cryptology

Greek: “krypto” = hide.

Cryptology is the science of hiding:

1. cryptography
2. cryptanalysis

## Goals of Cryptography 

Cryptography is the science that enables Alice and Bob to communicate securely in the presence of Eve.

1. Confidentiality
   * Only who should see would see.
2. Data integrity
   * Data would be as it is.
3. Authentication
   * Entity authentication \(Identification\) 
     * People who would see should be who should see.
   * Message authentication \(Data origin authentication\)
     * Data should be from where is should be.
4. Non-repudiation
   * Prevention of denial of previous commitments or actions 

Solutions: Protocols between Alice and Bob At least one of Alice or Bob needs to know more \(or can do more\) than Eve

## Attacker \(Cryptanalyst\) Model

Passive: The attacker does not modify the data, only monitors the communication. It threatens confidentiality.

* Example: listen to the communication between Alice and Bob, and if it’s encrypted try to decrypt it. 

Active: The attacker is actively involved in inserting, deleting, or modifying data. It threatens authentication and confidentiality.

## Terminology

* plaintext - the original message
* ciphertext - the coded message
* cipher - algorithm for transforming plaintext to ciphertext
* key - info used in cipher known only to sender/receiver
* encipher \(encrypt\) - converting plaintext to ciphertext
* decipher \(decrypt\) - recovering ciphertext from plaintext

## Kerckhoff’s Principle

1. Security should depend only on the key.
   * Don’t assume enemy won’t know algorithm.
2. Security by obscurity doesn’t work.
   * Look at history of examples.
   * Better to have scrutiny by open experts.

## Attacks on encryption schemes 

* Ciphertext-only attack: deduce the decryption key or plaintext by only observing ciphertext. 
* Known-plaintext attack： using a quantity of plaintext and corresponding ciphertext. 
* Chosen-plaintext attack： chooses plaintext and is then given corresponding ciphertext. 
* Adaptive chosen-plaintext attack: chosen-plaintext attack where the choice of plaintext may depend on the ciphertext received from previous requests. 
* Chosen-ciphertext attack: selects the ciphertext and is then given the corresponding plaintext. 
* Adaptive chosen-ciphertext attack: chosen-ciphertext attack where the choice of ciphertext may depend on the plaintext received from previous requests.

