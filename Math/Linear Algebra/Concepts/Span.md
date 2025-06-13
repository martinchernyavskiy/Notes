## Definition
?
*Let $S \subset V$ be a subset, then Span(S) is the set of all linear combinations of elements in S in the form:
$Span(S) = \{a_{1}v_{1}+\dots a_{k}v_{k}|a_{1},\dots,a_{k} \in R, u_{1},\dots u_{k} \in S\}$*
<!--SR:!2025-06-28,15,292-->

## Examples
?
- $S=\{\vec{0}\}, \quad Span(S) = \{\vec{0}\}$
- $S=V, \quad Span(S) = V$
- $Span(\{(1,0),(0,1)\}) = \{a_{1}(1,0)+a_{2}(0,1)|a_{1},a_{2} \in R\} = \{(a_{1},a_{2})|a_{1},a_{2} \in R\} = R^2$
- $Span(\{(1,m)\}) = \{a_{1}(1,m)|a_{1} \in R\} = \{(a_{1},ma_{1})|a_{1} \in R\} = L_{m}$
.
- $Span(\{(1,0,0),(0,0,1)\})=\{(a_{1},0,a_{2})|a_{1},a_{2} \in R\}$
	= xz-plane in $R^3$
<!--SR:!2025-06-28,15,292-->

## Worked-Out Examples
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
	\end{pmatrix}$$
	Since there are solutions, the vector is in the span.
<!--SR:!2025-06-29,16,296-->

## $S \subset V$ generates V if Span(S) = V
?
- Examples of generative subsets:
	1. {(1,0), (0,1)}, generates $R^2$
	2. $\{\begin{pmatrix}1 & 0 \\ 0 & 0\end{pmatrix}, \begin{pmatrix}0 & 0 \\ 0 & 1\end{pmatrix}, \begin{pmatrix}0 & 1 \\ 1 & 0\end{pmatrix}\}$, generates v.s of $2\times_{2}$ symmetric matrices:
    A = $\begin{pmatrix} a_{11} & a_{12} \\ a_{12} & a_{22}\end{pmatrix}$ = $a_{11}\begin{pmatrix}1 & 0 \\ 0 & 0\end{pmatrix} + a_{21}\begin{pmatrix}0 & 0 \\ 0 & 1\end{pmatrix} + a_{12}\begin{pmatrix}0 & 1 \\ 1 & 0\end{pmatrix}$
<!--SR:!2025-06-29,16,290-->

## Column Space of Matrix
?
- Consider an arbitrary [[Matrix (Matrices)]] $A \in M_{m\times n}$
- View it as a collection of n-column vectors in $R^m$
- Then $Col(A) = Span\{\begin{pmatrix}a_{11} \\ \vdots  \\ a_{m1}\end{pmatrix} \dots \begin{pmatrix}a_{1n}  \\ \vdots  \\ a_{mn}\end{pmatrix}\}$, a subspace of $R^m$
- ![[Pasted image 20250608180710.png]]
<!--SR:!2025-06-24,11,270-->

## Theorems
- [[Span of a non-empty subset is a subspace]]


#linear-algebra