# Public Key Infrastructure

## Summary of the Problem

* How are public key stored
* How to obtain the public key
* How does Bob know or 'trusts' that $$P_A$$is Alice's public key

## Key Distribution

* Eve creates a keypair \(private/public\) and declare the public key belongs to Bob
* People send confidential stuff to Bob
* Eve reads Bob's messages
* Bob does not have the private key to read them

## Key Verification

Two approaches:

1. Meet in person ro call him to check you have to right one
   * Fingerprint or hash of the key can be checked on the phone
2. Get someone you already trust to certify that the key belongs to Bob
   * By checking for a trusted digital signature on the key

## Trust Models

### PGP

Web-of-Trust \(PGP\)

* Peer-to-peer model
* Individuals digitally sign each other keys
* You would implicitly trust keys signed by some of your friends

#### Issues

Time-consuming, requires lots of work and general public doesn’t understand it.

### CAs

Trusted Authority + Path of Trust \(CAs\) is

* Everyone trusts the root Certificate Authority \(e.g., Verisign\)
* CA digitally signs keys of anyone having checked their credentials by traditional methods
* CA may even nominate others to be CAs – and you would trust them automatically, too

#### Issues

CAs tend to be a little bit like a big brother as we all have to trust them implicitly.

* But it is a simpler model, easier to deploy and manage

## Certificates

The simplest certificate just contains: 

* Information about the entity that is being certified to own a public key
* That public key 

And all of this is digitally signed by someone trusted \(like your friend or a CA\).

### Authentication with Certificates

1. Alice gets Bobs certificate
2. She verifies its digital signature 
3. Alice challenges Bob to encrypt for her a phrase etc. she just made up \(“I am Bob and not Eve”\) 
4. Bob has, of course, the private key that matches the certificate, so he responds 
5. Alice decrypts this with the public key she has in the certificate \(which she trusts\) and if it matches the phrase she challenged Bob with then it must really be Bob himself! 

That’s the basic concept of how SSL works.

### Advantages

Certificates are “safe”

* No need to protect them too much, as they are digitally signed
* Store anywhere, a file or a “dumb” memory-only smartcard

### Certification Hierarchy

Most organisations do not use just one root key for signing certificates

* Dangerous, if that one key is compromised
* Does not scale to large organisations
* Difficulty in managing responsibility

Certificate Hierarchies

* Start with CA root cert
* Create more keys \(e.g. for Microsoft etc.\), sign with root key, mark as subordinate CAs
* Create more levels in your organisation \(for departments etc.\) 

Validating a cert possibly involves validating a path of trust

### Certificate Revocation

* Keys get compromised, as a fact of life 
* You or your CA issue a certificate revocation certificate
  * Must be signed by CA, of course 
* And you do everything you can to let the world know that you issued it 
* This is not easy
  * Certificate Revocation Lists \(CRL\) are used
  * They require that the process of cert validation actively checks the CRL and keep it up-to-date
  * There are some scalability issues
  * Many people disable this function 
* That is why short expiration policies are important

