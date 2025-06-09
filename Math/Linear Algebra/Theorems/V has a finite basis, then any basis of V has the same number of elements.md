### Theorem: If V has a finite basis, then any basis of V has the same number of elements
?
#### Proof: 
Let $\beta$ be a finite basis with n elements. Let $\bar{\beta}$ be another basis. We claim that $\bar{\beta}$ is finite.
If $\bar{\beta}$ is not, then it contains a set $\bar{U}$ of $n+1$ linearly independent vectors. Applying [[Replacement Theorem]], $S=\beta, \mathcal{U}=\bar{U} \to n+1\leq n$, so contradiction.
Applying Replacement Theorem again for $(S=\beta, \mathcal{U}=\beta) \to \text{size of }\beta \leq  n$
Then again for $(S=\bar{\beta}, )$
This completes the proof. $\square$
