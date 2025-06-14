
## Definition
?
*Recall $A \in M_{m \times n}$ defines a linear map $L_{A}: \mathbb{R}^n \to \mathbb{R}^m$
$\bar{x} \to A \bar{x}$. 
Any linear map between finite dimensional vector spaces can be represented by a matrix.*

## Additional Definitions
?
- $[v]_{\beta}=(a_{1},\dots,a_{n}) \in \mathbb{R}^n$ is a coordinate expression for v with respect to $\beta$
.
- Each basis $\beta$ of V (w/ dim(V) = n) gives a map that identifies V with $\mathbb{R}^n$
.
- Consider $T: V \to W$ linear, V, W finite dimensional
		Let $\beta = \{ v_{1},\dots,v_{n} \}$ be a basis for V and let $\gamma = \{ w_{1},\dots ,w_{m} \}$ be a basis for W
		For $v \in V$ we then have $T(v)= a_{1}w_{1}+\dots+a_{m}w_{m}$
		For $v_{j}$, we have $T(v_{j})=a_{1j}w_{1}+\dots+a_{mj}w_{m}$
		$[T]_{\beta}^\gamma = (a_{ij})$ $i=1,\dots,m$, $j=1,\dots,n$
- $[T]_{\beta}^\gamma$ is a matrix representation o T with respect to the bases $\beta, \gamma$

## Examples
?
Ex: $T_{d}: P_{3} \to P_{2}$
	$f \to f^1$
Ex: $T_{i}: P_{2} \to P_{3}$
	$f \to \int_{0}^x{f(t)dt}$
‎Ex: $V = \mathbb{R}^2$, $v=(2,1)$
	$\beta=\{ (1,0),(0,1) \}$
	$\beta^1=\{ (1,1),(1,-1) \}$
	$[v_{\beta}]=(2,1), [v_{\beta^1}]=(a_{1},a_{2})=(\frac{3}{2}, \frac{1}{2})$
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
	$[]_{\beta}: V \to \mathbb{R}^n$ is linear, 1-1 and onto
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