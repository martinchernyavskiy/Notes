## Definition
?
*Let $S \subset V$ be a subset, then Span(S) is the set of all linear combinations of elements in S in the form:
$Span(S) = \{a_{1}v_{1}+\dots a_{k}v_{k}|a_{1},\dots,a_{k} \in R, u_{1},\dots u_{k} \in S\}$*

## Properties / Axioms
?
1. ...
2. ...
3. ...

## Examples
?
- $S=\{\vec{0}\}, \quad Span(S) = \{\vec{0}\}$
‎.
- $S=V, \quad Span(S) = V$
‎.
- $Span(\{(1,0),(0,1)\}) = \{a_{1}(1,0)+a_{2}(0,1)|a_{1},a_{2} \in R\} = \{(a_{1},a_{2})|a_{1},a_{2} \in R\} = R^2$
.
- $Span(\{(1,m)\}) = \{a_{1}(1,m)|a_{1} \in R\} = \{(a_{1},ma_{1})|a_{1} \in R\} = L_{m}$
.
- $Span(\{(1,0,0),(0,0,1)\})=\{(a_{1},0,a_{2})|a_{1},a_{2} \in R\}$
	= xz-plane in $R^3$

## Worked-examples
?
- Is $x^3-3x+5$ in $Span(\{x^3+2x^2-x+1, x^3+3x^2-1\})?$
	$x^3-3x+5=a_{1}(x^3+2x^2-x+1)+a_{2}(x^3+3x^2-1)$
	$x^3-3x+5=(a_{1}+a_{2})x^3+(2a_{1}+3a_{2})x^2-a_{1}x+(a_{1}-a_{2})$
	Converting to Augmented Matrix gives:
	$$\begin{pmatrix}
	1 & 1 & 1 \\
	2 & 3 & 0 \\
	-1 & 0 & -3 \\
    1 & -1 & 5
	\end{pmatrix}
	\to
	\begin{pmatrix}
	1 & 1 & 1 \\
	0 & 1 & -2 \\
	0 & 1 & -2 \\
    0 & -2 & 4
	\end{pmatrix}
	\to
	\begin{pmatrix}
	1 & 1 & 1 \\
	0 & -1 & -2 \\
	0 & 0 & 0 \\
    0 & 0 & 0
	\end{pmatrix}
$$
	Since there are solutions, the vector is in the span.

## Remarks 
?
- $S \subset V$ generates V if Span(S) = V
	Examples of generative subsets:
		1. {(1,0), (0,1)}, generates $R^2$
		2. {(), (), ()}, generates v.s of $2\times_{2}$ symmetric matrices
			A = $\begin{pmatrix} a_{11} & a_{12} \\ a_{12} & a_{22}\end{pmatrix}$ = $a_{11}\begin{pmatrix}1 & 0 \\ 0 & 0\end{pmatrix} + a_{21}\begin{pmatrix}0 & 0 \\ 0 & 1\end{pmatrix} + a_{12}\begin{pmatrix}0 & 1 \\ 1 & 0\end{pmatrix}$

## Theorems
- [[Span of a non-empty subset is a subspace]]
- [[Theorem Name 2]]

## Questions
- ...
- ...
- ...



#linear-algebra