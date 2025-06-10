### Theorem: If V has a finite basis, then any basis of V has the same number of elements
?
#### Proof: 
Let $\beta$ be a finite basis with n elements. Let $\bar{\beta}$ be another basis. We claim that $\bar{\beta}$ is finite.
If $\bar{\beta}$ is not, then it contains a set $\bar{U}$ of $n+1$ linearly independent vectors. Applying [[Replacement Theorem]], $S=\beta, \mathcal{U}=\bar{U} \to n+1\leq n$, so contradiction.
Applying Replacement Theorem again for $(S=\beta, \mathcal{U}=\bar{\beta}) \to \text{size of }\bar{\beta} \leq  n$
Then again for $(S=\bar{\beta}, \mathcal{U}=\beta) \to n\leq \text{size of } \bar{\beta}$
$\to \text{ size of } \bar{\beta}=n$
Hence, $\beta \text{ and } \bar{\beta}$ have the same number of elements.
This completes the proof. $\square$
