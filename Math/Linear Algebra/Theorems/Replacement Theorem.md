### Theorem: Suppose $S=\{s_{1},\dots s_{n}\}$ generates V. If $\mathcal{U} = \{u_{1},\dots u_{k}\}$ is linearly independent, then $k\leq n$ and there is a subset $\mathcal{T}\subset S$ of size $n-k$ such that $Span(\mathcal{U}\cup \mathcal{T})=V$
?
#### Proof: 
By induction on k: 
**Base case:** k=0, i.e $\mathcal{U}=\emptyset$, there $k\leq n$, since $n-k=n$ and $\mathcal{T}=S$
**Inductive Step:** Assume true for j. Need to show true for j+1.
Given $\mathcal{U}_{j+1}=\{u_{1},\dots,u_{j+1} \}$ linearly independent. We need $j+1\leq n$ and $\mathcal{T}_{j+1}\subset S$ such that $Span(\mathcal{U}_{j+1}\cup \mathcal{T}_{j+1})=V$ where size $\mathcal{T}_{j+1}=n-j-1$ 
Note $\mathcal{U}_j=\{u_1,\ldots,u_j\}$ is linearly independent.
By inductive hypothesis we know $j\leq n$ and there is a $\mathcal{T}_j=\{s_1,\ldots,s_{n-j}\}$ such that Span$\big(\{u_1,\ldots,u_j,s_1,\ldots,s_{n-j}\}\big)=V\ni u_{j+1}$ From this it follows that
$u_{j+1}=a_1u_1+\ldots+a_ju_j+b_1s_1+\ldots+b_{n-j}s_{n-j}$ (*) 
Note $b_1,\ldots,b_{n-j}$ are not all zero(Assume $b_{n-j}\neq 0$) So $n-j\geq 1\Longleftrightarrow n-j-1\geq 0\Rightarrow n\geq j+1$ (as desired) (*) $\Rightarrow s_{n-j}\in$ $Span$$\big(\{u_1,\ldots,u_j,u_{j+1},s_1,\ldots,s_{n-j-1}\}\big)$ $b_{n-j}\neq 0$
If Span$\big(\{u_1,\ldots,u_j,u_{j+1},\underbrace{s_1,\ldots,s_{n-j-1}}_{\mathcal{T}_{j+1}}\}\big)=V$, then we are done.
Span$\big(\{u_1,\ldots,u_j,u_{j+1},s_1,\ldots,s_{n-j-1}\}\big)$
= Span$\big(\{u_1,\ldots,u_j,u_{j+1},s_1,\ldots,s_{n-j-1},s_{n-j}\}\big)$ (by HWK3, Q2)
= Span$\big(\{u_1,\ldots,u_j,s_1,\ldots,s_{n-j-1},s_{n-j}\}\big)$ (by * and HWK3, Q2)
= Span($\mathcal{U}_j\cup\mathcal{T}_j)=V$
$\mathcal{T}_{j+1}=\{s_1,\ldots,s_{n-j-1}\}$
done
This completes the proof. $\square$

### Immediately follow:

#### 1.
#### 2.

Notes:

There is a subset of V that generates it and there is a linearly independent subset for which taking the union of the excess of the vectors in the generating subset, generates the same vector space. 

Case 1: Generating subset is a basis
	In this case the difference in number of vectors is 0, and all basis should have same number of vectors, hence U is a basis also, generating V.
Case 2: U is empty, hence taking union with the whole subset S spans V.
Case 3: Intermediate
	Assuming true for j, we need to show that it's true for j+1
	U has j+1 number of vectors, hence we need to show that that number of vectors is less than n and taking the span of those vectors and n-j-1 vectors from S spans V.
	From hypothesis, U must be linearly independent, we know that if we remove a vector from linearly independent subset, then that subset is still linearly independent, Hence $U_{j}$ is linearly independent.
	Thus, by inductive hypothesis, taking span of vectors in $U_{j}$ with n-j vectors from S spans V.
	We know however that $u_{j+1}$ vector belongs to V since it can be expressed as a linear combination of that union subset. 
	So $u_{j+1} = a_{1}u_{1}+\dots+a_{j}u_{j}+b_{1}s_{1}+\dots+b_{n-j}s_{n-j}$
	coefficients of s vectors must not all be zero
Since vectors in $U_{j}$ are linearly independent, $u_{j+1}$ can't be expressed as a linear combination of them. 