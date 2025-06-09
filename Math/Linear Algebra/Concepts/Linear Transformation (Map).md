## Definition
?
*A map T from a vector space V to a vector space W $(T: V \to W)$ is linear for all $v_{1},v_{2} \in V \text{ and } c \in \mathbb{R}$. if the following hold:*
## Properties / Axioms
1. $T(v_{1}+v_{2}) = T(v_{1})+T(v_{2})$
2. $T(cv_{1}) = cT(v_{1})$
	.
	Following the 2 properties, the transformation is linear iff:
	$T(v_{1}+cv_{2}) = T(v_{1})+cT(v_{2})$ for $v_{1},v_{2} \in V \text{ and } c \in \mathbb{R}$
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
	Done if $T(\vec{0_{V}}) + \vec{0_{W}}$
	Want $(c) \to T(\vec{0_{V}}) =\vec{0_{W}}$
	$$
\begin{aligned}
\vec{0_{W}} + \cancel{T(\vec{0})}
\end{aligned}
$$

## Examples
?
- Transpose: $M_{m\times n} \to M_{n\times m}$
	Given a general [[Matrix (Matrices)]], transpose of this matrix depicted as $A^t$ = ($a^t_{ij}=a_{ji}$)
‎ 
- Example 2: ...
‎ 
- Example 3: ...

## Worked-Out Examples
?
- Example 1

## Non-examples
?
- Non-example 1: ...
- Non-example 2: ...

## Theorems
- [[Theorem Name 1]]
- [[Theorem Name 2]]

## Questions
- ...
- ...
- ...



#linear-algebra