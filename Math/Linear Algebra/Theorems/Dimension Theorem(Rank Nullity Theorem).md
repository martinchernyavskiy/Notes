### Theorem: If $T:V \to W$ is linear and V is finite dimensional, then $dim(N(T))+dim(R(T))=dim(V)$, $nullity + rank$ of T respectively
?
#### Proof: 
Set $dimV=n$
$N(T)$ is a subspace of V of $dim \space k\leq n$ by [[Dimension of Subspace Is At Most The Dimension of Vector Space]]
Let $\beta_{N}=\{ u_{1},\dots,u_{k} \}$ be a basis of N(T)
Claim 1: We can extend $\beta_{N}$ by n-k vectors to form a basis of V
Let $\beta=\{ v_{1},\dots,v_{n} \}$ be a basis for V.
By [[Replacement Theorem]], ($S=\beta, \mathcal{U}=\beta_{N}$) $\to$ We can add n-k elements of $\beta$ to $\beta_{N}$ so that the resulting set generates V.
$Span(\{ u_{1},\dots,u_{k},v_{1},\dots,v_{n-k} \})=V$
$\beta_{V}$ is a basis for V ([[Refinement Theorem]])
Claim 2: $\{ T(v_{1}),\dots,T(v_{n-k}) \}$ is a basis for R(T) with this we will be done.
$dim(N(T))+dim(R(T) = k+(n-k))=n=dim(V)$
To prove Claim 2:
$\{ T(v_{1}),\dots,T(v_{n-k}) \} \subset R(T)$, to show it is linearly independent:
$a_{1}T(v_{1})+\dots+a_{n-k}T(v_{n-k})=\vec{0_{W}}$
$\to T(a_{1}v_{1}+\dots+a_{n-k}v_{n-k})=\vec{0_{W}}$
$\to a_{1}v_{1}+\dots+a_{n-k}v_{n-k} \in N(T)$
$\to a_{1}v_{1}+\dots+a_{n-k}v_{n-k} \in Span(u_{1},\dots,u_{k})$
$\to a_{1}=0,\dots, a_{n-k}=0$ since $\{ u_{1},\dots,u_{k},v_{1},\dots v_{n-k} \}$ is linearly independent.
Need to show $Span(\{ T(v_{1}),\dots,T(v_{n-k}) \}= R(T))$
$R(T)=\{ T(v)|v \in V \}$
$$
\begin{aligned}
&= \{ T \}\\
&=
\end{aligned}
$$
This completes the proof. $\square$

### Immediately follow:

#### 1.
#### 2.