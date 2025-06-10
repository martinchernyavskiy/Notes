### Theorem: Suppose $S=\{s_{1},\dots s_{n}\}$ generates V. If $\mathcal{U} = \{u_{1},\dots u_{k}\}$ is linearly independent, then $k\leq n$ and there is a subset $\mathcal{T}\subset S$ of size $n-k$ such that $Span(\mathcal{U}\cup \mathcal{T})=V$
?
#### Proof: 
By induction on k: 
**Base case:** k=0, i.e $\mathcal{U}=\emptyset$, there $k\leq n$, since $n-k=n$ and $\mathcal{T}=S$, $Span(\mathcal{U}\cup \mathcal{T})=V$
**Inductive Step:** Assume true for j. Need to show true for j+1.
Given $\mathcal{U}_{j+1}=\{u_{1},\dots,u_{j+1} \}$ linearly independent. We need $j+1\leq n$ and $\mathcal{T}_{j+1}\subset S$ such that $Span(\mathcal{U}_{j+1}\cup \mathcal{T}_{j+1})=V$ where size $\mathcal{T}_{j+1}=n-j-1$ 
Note $\mathcal{U}_j=\{u_1,\ldots,u_j\}$ is linearly independent.
By inductive hypothesis we know $j\leq n$ and there is a $\mathcal{T}_j=\{s_1,\ldots,s_{n-j}\}$ such that Span$\big(\{u_1,\ldots,u_j,s_1,\ldots,s_{n-j}\}\big)=V\ni u_{j+1}$ From this it follows that
$u_{j+1}=a_1u_1+\ldots+a_ju_j+b_1s_1+\ldots+b_{n-j}s_{n-j}$ 
Note $b_1,\ldots,b_{n-j}$ are not all zero(Assume $b_{n-j}\neq 0$) So $n-j\geq 1\Longleftrightarrow n-j-1\geq 0\Rightarrow n\geq j+1$ (as desired) $\Rightarrow s_{n-j}\in$ $Span$$\big(\{u_1,\ldots,u_j,u_{j+1},s_1,\ldots,s_{n-j-1}\}\big)$ $b_{n-j}\neq 0$
If Span$\big(\{u_1,\ldots,u_j,u_{j+1},\underbrace{s_1,\ldots,s_{n-j-1}}_{\mathcal{T}_{j+1}}\}\big)=V$, then we are done.
Span$\big(\{u_1,\ldots,u_j,u_{j+1},s_1,\ldots,s_{n-j-1}\}\big)$
= Span$\big(\{u_1,\ldots,u_j,u_{j+1},s_1,\ldots,s_{n-j-1},s_{n-j}\}\big)$ (by HWK3, Q2)
= Span$\big(\{u_1,\ldots,u_j,s_1,\ldots,s_{n-j-1},s_{n-j}\}\big)$ (by * and HWK3, Q2)
= Span($\mathcal{U}_j\cup\mathcal{T}_j)=V$
$\mathcal{T}_{j+1}=\{s_1,\ldots,s_{n-j-1}\}$
done
This completes the proof. $\square$

Notes:

Theorem: Suppose there is a subset that generates V (it can be either basis or lin dependent). Then if there is another linearly independent subset (one that is or isn't generating V), then the number of