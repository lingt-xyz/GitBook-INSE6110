# Knapsack

Based on Subset sum problem\(NP-complete\):

select a subset sum problem that is easy to solve \(super increasing sequence\)  then disguise it as an instance of the general subset sum problem which is hopefully difficult to solve.

## Key

* The original knapsack set can serve as the private key
* while the transformed knapsack set serves as the public key.

Most Knapsack proposals are broken.

## Knapsack Problem

Let $$I=\{0,1,\dots,n-1\}$$. Given the integer vector $$A=\{a_0,a_1,\dots,a_{n-1}\}$$and another integer $$X$$, is there a $$J\subseteq I$$such that

$$
\sum_{i\in J}{a_i}=X
$$

## Easy Knapsack Problem

If the numbers $$a_i$$have the superincreasing property, i.e.:

$$
\sum_{i=0}^{j-1}{a_i}< a_j
$$

then the knapsack problem is easy.

### Example

$$A=\{1,2,4,8,16\}$$; superincreasing $$1<2;1+2<4;1+2+4<8;1+2+4+8<16$$.

Let $$X=23$$. Solution is found by computing the binary expansion of $$X=23=(10111)_2$$, thus $$1+2+4+16=23$$.

## Hard Knapsack Problem

Without the superincreasing property the knapsack problem \(in general\) is hard.

## Trapdoor knapsack

* Take an easy knapsack and disguise it.

Example: $$A={1,2,4,8,16}$$. 

1. Select a prime $$p$$larger than the sum $$31$$, for example $$p=37$$. 
2. Select $$t$$and compute $$t^{-1}$$mod $$p$$, for example, $$t=17$$and $$t^{-1}=24$$.
3. Produce a new knapsack vector $$B$$from $$A$$such that $$b_i\equiv a_it\pmod p$$. This gives $$B=\{17,34,31,25,13\}$$.

However, with the special trapdoor information$$t=17,t^{-1}=24$$, and$$p=37$$, we can convert this problem to the easy version.

### Example

Given $$B$$and $$X=72$$, is there a subset of $$B$$summing to $$X$$?

Solve the easy knapsack with $$X'$$:$$X'\equiv Xt^{-1}\pmod {37}=26=(11010)_2$$.$$A=\{1,\underline{2},4,\underline{8},\underline{16}\}$$, thus $$X'=26=2+8+16$$.

This gives the hard knapsack: $$B=\{17,\underline{34},31,\underline{25},\underline{13}\}$$and $$X=72=34+25+13$$.

## Application

**User R**: Publishes $$B=\{17,34,31,25,13\}$$. Keeps $$A=\{1,2,4,8,16\},t=17,t^{-1}=24$$, and $$p=37$$private.

**User S**: Wants to send the message $$m=12$$to User R.

1. $$m=12=(01100)_2$$
2. $$c=0\cdot17+1\cdot34+1\cdot31+0\cdot25+0\cdot13=65$$.
3. send $$c=65$$to User R.

**User R**: Recivies $$c=65$$

1. compute $$c'=65t^{-1}=65\cdot24\equiv 6\pmod37$$.
2. Solves the easy knapsack problem: $$6=0\cdot1+1\cdot2+1\cdot4+0\cdot8+0\cdot16$$
3. The gives the message as $$(01100)_2=12$$.

