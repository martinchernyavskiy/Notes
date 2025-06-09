### Theorem: Suppose $S=\{s_{1},\dots s_{n}\}$ generates V. If $\mathcal{U} = \{u_{1},\dots u_{k}\}$ is linearly independent, then $k\leq n$ and there is a subset $\mathcal{T}\subset S$ of size $n-k$ such that $Span(\mathcal{U}\cup \mathcal{T})=V$
?
#### Proof: 
By induction on k: 
**Base case:** k=0, i.e $\mathcal{U}=\emptyset$, there $k\leq n$, since $n-k=n$ and $\mathcal{T}=S$
**Inductive Step:** Assume true for j. Need to show true for j+1.
Given $\mathcal{U}_{j+1}=\{u_{1},\dots,u_{j+1} \}$ linearly independent. We need $j+1\leq n$ and $\mathcal{T}_{j+1}\subset S$ such that $Span(\mathcal{U}_{j+1}\cup \mathcal{T}_{j+1})=V$ where size $\mathcal{T}_{j+1}=n-j-1$ 

This completes the proof. $\square$

### Immediately follow:

#### 1.
#### 2.