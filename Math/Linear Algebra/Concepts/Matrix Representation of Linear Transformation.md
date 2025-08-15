
## Definition
?
*Recall $A \in M_{m \times n}$ defines a linear map $L_{A}: \mathbb{R}^n \to \mathbb{R}^m$
$\bar{x} \to A \bar{x}$.
Any linear map between finite dimensional vector spaces can be represented by a matrix.*
<!--SR:!2025-08-19,4,270-->

## Additional Definitions
?
- Each basis $\beta$ of V (w/ dim(V) = n) gives a map that identifies V with $\mathbb{R}^n$
.
- $[v]_{\beta}=(a_{1},\dots,a_{n}) \in \mathbb{R}^n$ is a coordinate expression for v with respect to $\beta$
.
- $[]_{\beta}: V \to \mathbb{R}^n$ is linear, 1-1 and onto
.
- Consider $T: V \to W$ linear, V, W finite dimensional
		Let $\beta = \{ v_{1},\dots,v_{n} \}$ be a basis for V and let $\gamma = \{ w_{1},\dots ,w_{m} \}$ be a basis for W
		For $v \in V$ we then have $T(v)= a_{1}w_{1}+\dots+a_{m}w_{m}$
		For $v_{j}$, we have $T(v_{j})=a_{1j}w_{1}+\dots+a_{mj}w_{m}$
		$[T]_{\beta}^\gamma = (a_{ij})$ $i=1,\dots,m$, $j=1,\dots,n$
- $[T]_{\beta}^\gamma$ is a matrix representation of T with respect to the bases $\beta, \gamma$
- $[T]_{\beta}^\gamma = \begin{pmatrix}| &  & | \\ [T(v_{1})]_{\gamma} & \dots & [T(v_{n})]_{\gamma} \\ | &  & |\end{pmatrix}$
<!--SR:!2025-08-18,3,250-->

## Examples
?
Ex: $T_{d}: P_{3} \to P_{2}$
	$f \to f^1$
Ex: $T_{i}: P_{2} \to P_{3}$
	$f \to \int_{0}^x{f(t)dt}$
‎Ex: $A \in M_{m \times n} \to L_{A}: \mathbb{R}^n \to \mathbb{R}^m$
	Claim: If $\beta$ and $\gamma$ are standard bases for $\mathbb{R}^n, \mathbb{R}^m$ respectively, then $[L_{A}]_{\beta}^\gamma = A$
	Proof: $\beta = \{ e_{1},\dots,e_{n} \}, e_{1} = \begin{pmatrix}1 \\ 0 \\ \vdots \\ 0\end{pmatrix}$
	$[L_{A}]_{\beta}^\gamma=([L_{A}(e_{1})]_{\gamma}\dots[L_{A}(e_{n})]_{\gamma})$
	$[L_{A}(e_{1})]_{\gamma} = [Ae_{1}]_{\gamma}=Ae_{1}$, the first column of A, etc.
	$\begin{pmatrix}2 \\ 1 \end{pmatrix} = 2\begin{pmatrix}1 \\ 0\end{pmatrix}+1\begin{pmatrix}0 \\ 1\end{pmatrix}$
<!--SR:!2025-08-19,4,272-->

## Worked-Out Examples
?
Ex: $V = \mathbb{R}^2$, $v=(2,1)$
	$\beta=\{ (1,0),(0,1) \}$
	$\beta^1=\{ (1,1),(1,-1) \}$
	$[v]_{\beta}=(2,1), [v_{\beta^1}]=(a_{1},a_{2})=(?, ?)$
	$(2,1)=a_{1}(1,1)+a_{2}(1,-1)$
	$a_{1}+a_{2}=2$
	$a_{1}-a_{2}=1$
	$$
\begin{pmatrix}
1 & 1 & 2 \\
1 & -1 & 1
\end{pmatrix}
\to
\begin{pmatrix}
1 & 1 & 2 \\
0 & -2 & -1
\end{pmatrix}
\to
\begin{pmatrix}
1 & 1 & 2 \\
0 & 1 & \frac{1}{2}
\end{pmatrix}
\to
\begin{pmatrix}
1 & 0 & \frac{3}{2} \\
0 & 1 & \frac{1}{2}
\end{pmatrix}
$$
	$[v_{\beta}]=(2,1), [v_{\beta^1}]=(a_{1},a_{2})=(\frac{3}{2}, \frac{1}{2})$
<!--SR:!2025-08-19,4,274-->

	
Ex: $T_{d}: P_{3} \to P_{2}$
	$\beta = \{ 1,x,x^2,x^3 \}$
	$\gamma = \{ 1, x, x^2 \}$
	$[T_{d}]_{\beta}^\gamma=$
$${\begin{array}{l}
[T_{d}(1)]_{\gamma}= [0]_{\gamma} = \begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}\\
[T_{d}(x)]_{\gamma}= [1]_{\gamma} = \begin{pmatrix}
1 \\
0 \\
0
\end{pmatrix}\\
[T_{d}(x^2)]_{\gamma}= [2x]_{\gamma} = \begin{pmatrix}
0 \\
2 \\
0
\end{pmatrix}\\
[T_{d}(x^3)]_{\gamma}= [3x^2]_{\gamma} = \begin{pmatrix}
0 \\
0 \\
3
\end{pmatrix} \\
[T_{d}]_{\beta}^\gamma = \begin{pmatrix}
0 & 1 & 0 & 0 \\
0 & 0 & 2 & 0 \\
0 & 0 & 0 & 3
\end{pmatrix}
\end{array}}
$$
Ex: $T_{i}: P_{2} \to P_{3}$
	$[T_{i}]_{\gamma}^\beta = \begin{pmatrix}0 & 0 & 0  \\ 1 & 0 & 0 \\ 0 & \frac{1}{2} & 0 \\ 0 & 0 & \frac{1}{3}\end{pmatrix}$

## Theorems
- Theorem 2.7: Let U,T be linear functions from V to W vector spaces over F, then:
	1. aT + U is linear
		(aT + U)(cx+y) = aT(cx+y) + U(cx+y)
					= acT(x)+aT(y) + cU(x) + U(y)
					= c(aT+U)(x) + (aT + U)(y)
					So, aT + U is linear.
	2. Using standard operations of addition and scalar multiplication for functions, the collection of all linear transformation from V to W is a vector space over F
		Since T0 is a zero vector, it's clear that collection of all linear transformations from V into W is a vector space over F
- [[Matrix Representation Relation]]
- Theorem 2.8: Let T,U : V --> W linear, and V, W finite-dimensional with bases beta, gamma respectively
	- $[T+U]_{\beta}^{\gamma} = [T]_{\beta}^{\gamma} + [U]_{\beta}^{\gamma}$
	- $[aT]_{\beta}^{\gamma} = a[T]_{\beta}^{\gamma}$

#linear-algebra