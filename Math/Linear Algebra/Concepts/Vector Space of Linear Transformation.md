
## Definition
?
*Given vector spaces V, W, we define a vector space:
$\mathcal{L}(V,W)=\{ T: V \to W \}$* *which is the set of all linear maps from V to W*

## Additional Definitions
?
From [[Composition of Linear Transformations is Linear]], we define Matrix Multiplication:
- Given $A \in M_{m \times n}$ and $B \in M_{n \times p}$ define:
	$(AB)_{ij}= \sum_{k=1}^{n}A_{ik}B_{kj}$
	Alternatively,
	AB = $A(\bar{b_{1}},\dots,\bar{b_{p}})$ = $(A\bar{b_{1}},\dots,A\bar{b_{p}})$
- *Kronecker delta $\delta_{ij}$ = 1 where i=j and 0 everywhere else*. Identity matrix is given by $(I_{n})_{ij} = \delta_{ij}$
- $A^k = A^{k-1}A$, $A^0=I_{n}$
## Examples
?
- $S \in \mathcal{L}(X, Y)$ and $T \in \mathcal{L}(Y, Z)$
	$X \xrightarrow{S} Y \xrightarrow{T} Z$ can define a composition
	$T\circ S: X \to Z$
	$x \to T(S(v))$
- $(AB)^t = B^tA^t$

## Worked-Out Examples
?
- $A = \begin{pmatrix}1 & 2 & 3 \\ 4 & 5 & 6\end{pmatrix}, B = \begin{pmatrix}1 & 2 \\ 1 & 2 \\ 2 & 1\end{pmatrix}$
  $A \bar{b_{1}} = \begin{pmatrix}1 & 2 & 3 \\ 4 & 5 & 6\end{pmatrix}\begin{pmatrix}1 \\ 1 \\ 2\end{pmatrix} =1\begin{pmatrix}1 \\ 4\end{pmatrix}+1\begin{pmatrix}2 \\ 5\end{pmatrix}+2\begin{pmatrix}3 \\ 6\end{pmatrix} = \begin{pmatrix}9 \\ 21\end{pmatrix}$
  $A \bar{b_{2}} = \begin{pmatrix}1 & 2 & 3 \\ 4 & 5 & 6\end{pmatrix}\begin{pmatrix}2 \\ 2 \\ 1\end{pmatrix} = \begin{pmatrix}9 \\ 24\end{pmatrix}$
  $AB = \begin{pmatrix} 9 & 9 \\ 21 & 24\end{pmatrix}$
## Theorems
- [[Composition of Linear Transformations is Linear]]
- [[Composition Properties]]
- [[Matrix Representation of Composition]]
- [[Matrix  Multiplication Properties]]


#linear-algebra