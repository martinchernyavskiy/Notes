	## Definition
?
*A map T from a vector space V to a vector space W $(T: V \to W)$ is linear for all $v_{1},v_{2} \in V \text{ and } c \in \mathbb{R}$. if the following hold:*
## Properties / Axioms
1. $T(v_{1}+v_{2}) = T(v_{1})+T(v_{2})$
2. $T(cv_{1}) = cT(v_{1})$
	.
	Following the 2 properties, the transformation is linear iff: $T(v_{1}+cv_{2}) = T(v_{1})+cT(v_{2})$ for $v_{1},v_{2} \in V \text{ and } c \in \mathbb{R}$
	.
	Short proof:
	$\to$ Assume T is linear, (1, 2 hold)
$$
\begin{aligned}
T(v_{1}+cv_{2}) &= T(v_{1})+T(cv_{2}) \\
&= T(v_{1}) + cT(v_{2})
\end{aligned}
$$
	$\leftarrow$ Assume $T(v_{1}+cv_{2}) = T(v_{1})+cT(v_{2})$
$$
\begin{aligned}
T(v_{1}+v_{2}) &= T(v_{1}+(1)v_{2}) = T(v_{1})+(1)T(v_{2}) \\
&= T(v_{1}) + T(v_{2}) \\
T(cv_{1}) &= T(\vec{0} + cv_{1}) = T(\vec{0_{V}})+cT(v_{1})
\end{aligned}
$$
	Done if $T(\vec{0_{V}}) = \vec{0_{W}}$
	Want $(c) \to T(\vec{0_{V}}) =\vec{0_{W}}$
	$$
\begin{aligned}
\vec{0_{W}} + \cancel{T(\vec{0_{V}})} &= T(\vec{0_{V}}) \\
&= T(\vec{0_{V}}+1\times\vec{0_{V}}) \\
&= T(\vec{0_{V}}) + 1T(\vec{0_{V}}) \\
&= T(\vec{0_{V}}) + \cancel{T(\vec{0_{V}})}
\end{aligned}
$$
	Last small remark is that applying linear transformation to a linear combination is a linear combination of transformations applied to each vector
<!--SR:!2025-06-17,4,270-->

## Examples
?
- Transpose: $M_{m\times n} \to M_{n\times m}$
	Given a general [[Matrix (Matrices)]], transpose of this matrix depicted as $A^t$ = ($a^t_{ij}=a_{ji}$)
‎ .
- For $V,W$ the map:
	$T_{0}:V \to W$ is linear
	$u \to \vec{0_{W}}$
	Proof: Need $T_{0}(v_{1}+cv_{2})=T_{0}(v_{1})+cT_{0}(v_{2})$
	$T_{0}(v_{1}+cv_{2})=\vec{0_{W}}$
	$T_{0}(v_{1})+cT_{0}(v_{2})=\vec{0_{W}}+c \vec{0_{W}}=\vec{0_{W}}$
‎ .
- For any V, the map $I_{V}:V \to V$ is linear
		$u \to u$
- $T:\mathbb{R}^2 \to \mathbb{R}^2$
		$(x, y) \to (-y, x)$ (rotate 90deg left)
$$
\begin{aligned}
T((x_{1},y_{1})+c(x_{2},y_{2})) &=T((x_{1}+cx_{2},y_{1}+cy_{2})) \\
&= (-y_{1}-cy_{2}, x_{1}+cx_{2}) \\
\\
T((x_{1},y_{1}))+cT((x_{2},y_{2})) &=(-y_{1},x_{1})+c(-y_{2},x_{2}) \\
&= (-y_{1},-cy_{2}, x_{1}+cx_{2})
\end{aligned}
$$
- $T:P \to P$
		$f(x) \to f^1(x)$ is linear
- $T: P_{n} \to P_{n-1}$
		$f(x) \to f^1(x)$
- $L_{A}: \mathbb{R}^n \to \mathbb{R}^m$
		$\bar{x} \to A\bar{x}$ is linear
- For $a<b$ define:
	$T_{a}^b: C^0(\mathbb{R}) \to \mathbb{R}$
		$f \to \int_{a}^{b}f(x)dx$
$$
\begin{array}{l}
T_{a}^{b}(f+cg)=\int_{a}^{b}(f(x)+cg(x))dx \\ \\
\overset{calculus}{\operatorname*{\operatorname*{\operatorname*{\operatorname*{=}}}}}\int_{a}^{b}f(x)dx+c\int_{a}^{b}g(x)dx=T_{a}^{b}(f)+cT_{a}^{b}(g).
\end{array}
$$
<!--SR:!2025-06-16,3,250-->


#linear-algebra