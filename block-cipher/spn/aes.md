# AES

## Overview

* Based on the SPN structure
  * a variable block size: $$128,192, 256$$bits
  * key size of $$128,192$$or $$256$$bits
  * variable number of rounds: $$10,12,14$$
    * AES -$$128 (n=10)$$
    * AES -$$192 (n=12)$$
    * AES -$$256 (n=14)$$

## Algorithm

1. State = X 
2. AddRoundKey\(State, Key0\) 
3. for $$r = 1$$ to $$Nr - 1 $$
   1. SubBytes\(State, S-box\) 
   2. ShiftRows\(State\) 
   3. MixColumns\(State\)
   4. AddRoundKey\(State, Keyr\) 
4. for $$Nr$$
   1. SubBytes\(State, S-box\) 
   2. ShiftRows\(State\) 
   3. AddRoundKey\(State, KeyNr\) 
5. Y = State

