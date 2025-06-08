
## Definition
*A subspace is a subset of a vector space such that 0 vector is in it and it's closed under addition and scalar multiplication*

## Properties / Axioms
1. $\vec{0}\in W$
2. $\forall w_{1},w_{2} \in W, \quad w_{1}+w_{2} \in W$
3. $\forall c \in F,\forall w \in W, \quad  cw\in W$

## Examples
?
- $L_{m}$ = {(x, y) | y = mx} = {(x, mx) | $x \in R$}
.
- $P_{k}$ is a subspace of $P_{k+1}$
.
- $C^0(R)$ is a subspace of $\mathcal{F}(R)$
	$\vec{0}x=0$ is continuous $\checkmark$
	$f,g$ continuous $\to f+g$ continuous $\checkmark$
	$f$ continuous $\to cf$ continuous $\checkmark$
.
- $W$ = {symmetric [[Matrix (Matrices)]]} $\subset M_{n\times n}$
	$\vec{0}=\vec{0^t} \in W \quad \checkmark$
	.
	Need $A, B \in W \to A+B \in W$. Recall $A=(a_{ij}),B=(b_{ij})$, then:
	$(a_{ij})=(a_{ji}),(b_{ij})=(b_{ji}) \quad \forall i,j$
	$\to a_{ij}+b_{ij}=a_{ji}+b_{ji} \to (A+B) = (A+B)^t \in W \quad \checkmark$
	.
	Need $A \in W \to cA \in W, \quad \forall c\in R$.
	Since $A \in W, (a_{ij})=(a{ji})$. Multiplying each side by an arbitrary scalar doesn't alter the equation, so $(ca_{ij})=(ca_{ji}) \to cA = (cA)^t \to cA \in W \quad \checkmark$


## Worked-examples
?
- $W=\{(t_{1}+t_{2}, t_{1}-t_{2}, t_{1}) | t_{1},t_{2}\in R\}$
	$W\subset R^3$. Since $R^3$ is a vector space, we must show that W is a subspace by verifying the properties.
	$\vec{0} = (0,0,0),\quad t_{1}=t_{2}=0 \to(0,0,0) \in W \quad \checkmark$
	Let $(t_{1}+t_{2}, t_{1}+t_{2}, t_{1})$ and $(s_{1}+s_{2}, s_{1}+s_{2}, s_{1})$ be elements of $W$. Then: $(t_{1}+t_{2}, t_{1}+t_{2}, t_{1}) + (s_{1}+s_{2}, s_{1}+s_{2} = ((t_{1}+s_{1})+(t_{2}+s_{2}), (t_{1}+s_{1})-(t_{2}+s_{2}),t_{1}+s_{1}) \in W \quad \checkmark$
	$c(t_{1}+t_{2}, t_{1}-t_{2}, t_{1}) = (ct_{1}+ct_{2}, ct_{1}-ct_{2}, ct_{1}) \in W \quad \checkmark$


## Non-examples
?
- $W=[0,1] \subset\mathbb{R}$, since $1+1\not\in W$
- $W = \mathbb{Z}\subset \mathbb{R}$, since $\pi*z\not\in \mathbb{Z}$
- $W=\{(t_{1}+t_{2}, t_{1}-t_{2}, t_{1}+1) | t_{1},t_{2}\in R\}$, since $\vec{0} \not \in W$


## Theorems
- [[Subspace is a Vector Space]]

