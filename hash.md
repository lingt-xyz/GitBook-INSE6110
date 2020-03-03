# Hash

1. Pre-image resistance \(one-way property\)
   * Given $$y$$, to find any pre-image $$x′$$ such that $$h(x′)=y$$.
   * But remember: there are no known provably one-way functions.
2. Second pre-image resistance \(Weak collision resistance\)
   * Given $$x$$, to find a 2nd-preimage $$x′$$ where $$x′≠x$$ such that $$h(x′)=h(x)$$.
3. Collision resistance \(Strong collision resistance\)
   * Find any $$x′,x$$ where $$x′≠x$$ such that $$h(x′)=h(x)$$.
   * Need to guess $$2^{n/2}$$ inputs before finding a collision \(birthday paradox\).

