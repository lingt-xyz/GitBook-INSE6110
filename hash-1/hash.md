# Hash

A hash function $$h:\{0,1\}*→ \{0,1\}^m$$

## Requirements for Cryptographic hash functions

1. Pre-image resistance \(one-way property\)
   * Given $$y$$, to find any pre-image $$x′$$ such that $$h(x′)=y$$.
   * But remember: there are no known provably one-way functions.
2. Second pre-image resistance \(Weak collision resistance\)
   * Given $$x$$, to find a 2nd-preimage $$x′$$ where $$x′≠x$$ such that $$h(x′)=h(x)$$.
   * Need to guess $$2^n$$inputs.
3. Collision resistance \(Strong collision resistance\)
   * Find any $$x′,x$$ where $$x′≠x$$ such that $$h(x′)=h(x)$$.
   * Need to guess $$2^{n/2}$$ inputs before finding a collision \(birthday paradox\).

## Some popular hash functions

### MD5

128-bit output

### SHA-1

160-bit output

### SHA-2

256-bit output

### SHA-3

Arbitrary output

## Data Integrity

Encryption does not protect data from modification by another party. 

Need a way to ensure that data arrives at destination in its original form as sent by the sender and it is coming from an authenticated source.





