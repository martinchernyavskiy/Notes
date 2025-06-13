### Theorem: If $T:V \to W$ is linear and V is finite dimensional, then $dim(N(T))+dim(R(T))=dim(V)$, $nullity + rank$ of T respectively

#### Proof: 
Set $dimV=n$
$N(T)$ is a subspace of V of $dim \space k\leq n$ by [[Dimension of Subspace Is At Most The Dimension of Vector Space]]
Let $\beta_{N}=\{ u_{1},\dots,u_{k} \}$ be a basis of N(T)
Claim 1: We can extend $\beta_{N}$ by n-k vectors to form a basis of V
Let $\beta=\{ u_{1},\dots,u_{n} \}$ be a basis for V.
By [[Replacement Theorem]], ($S=\beta, \mathcal{U}=\beta_{N}$) $\to$ We can add n-k elemenets of $\beta$ to $\beta_{N}$ so that the resulting set generates V.
$Span(\{ u_{1},\dots,u_{k},v_{1},\dots,v_{n-k} \})=V$
$\beta_{V}$ is a basis for V ([[Refinement Theorem]])

This completes the proof. $\square$

### Immediately follow:

#### 1.
#### 2.