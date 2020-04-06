# Digital Signature

## Services Provided

1. Authentication
2. Data integrity
3. Non-Repudiation \(MAC does not provide this.\)

|  | Hash | Signature\(Public key\) | MAC\(Symmetric key\) |
| :--- | :--- | :--- | :--- |
| Authentication |  | ✔  | ✔  |
| Data integrity | ✔  | ✔  | ✔  |
| Non-Repudiation |  | ✔  |  |

## Cryptanalysis

* Key-only attack: Adversary knows only the verification function \(which is supposed to be public\).
* Known message attack: Adversary knows a list of messages previously signed by Alice. 
* Chosen message attack: Adversary can choose what messages wants Alice to sign, and he knows both the messages and the corresponding signatures.

## Adversarial Goals

* Total break: adversary is able to find the secret for signing, so he can forge then any signature on any message. 
* Selective forgery: adversary is able to create valid signatures on a message chosen by someone else, with a significant probability. 
* Existential forgery: adversary can create a pair \(message, signature\), s.t. the signature of the message is valid. 

A signature scheme **cannot** be perfectly secure; it can only be **computationally** **secure**. Given enough time and adversary can always forge Alice’s signature on any message.

## Digital Signatures and Hash

Very often digital signatures are used with hash functions, hash of a message is signed, instead of the message.

