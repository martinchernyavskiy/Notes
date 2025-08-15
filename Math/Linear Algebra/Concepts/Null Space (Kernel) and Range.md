
## Definitions
?
*Suppose $T:V \to W$ is linear.
Null Space (Kernel) of $T$ is:
$N(T)=\{ v \in V|T(v) = \vec{0_{W}} \} \subset V$
Range (Image) of $T$ is:
$R(T) = \{ T(v) | v \in V \} \subset W$*
<!--SR:!2025-08-29,14,290-->


## Additional Definitions
?
- $T:V \to W$ is onto if $R(T)=W$ or $\forall w \in W, \exists v \in V$ s.t $T(v)=w$
- $T:V \to W$ is 1-1 if
  $T(v_{1})=T(v_{2}) \to v_{1}=v_{2}$
<!--SR:!2025-08-19,4,272-->

## Examples
?
- $N(T_{a}^{b}) = \{ \text{functions in } C^0(\mathbb{R}) \text{ whose average over } [a,b] \text{ is } 0 \}$
- $R(T_{a}^b) =\mathbb{R} \quad (T_{a}^b \text{ is onto})$
‎
- For [[Dimension Theorem(Rank Nullity Theorem)]]
  $T:\mathbb{R}^n \to \mathbb{R}^n$
  $(x_{1},\dots,x_{n}) \to (x_{1},\dots,x_{m},0,\dots,0) \quad (m<n)$
  $N(T)=\{ (x_{1},\dots,x_{n})|x_{1}=0,\dots,x_{m}=0 \}$
  $dim(N(T))=n-m$
  $R(T)=\{ (x_{1},\dots,x_{m},0,\dots,0) \}$
  $dim(N(T)) = m$
  $dimN(T)+dimR(T)=(n-m)+m=n=dim\mathbb{R}^n$
<!--SR:!2025-08-19,4,277-->

## Theorems
- [[Kernel and Range are Subspaces given a Linear Transformation]]
- Theorem 2.2, R(T) = span(T($\beta$))
- [[Dimension Theorem(Rank Nullity Theorem)]]
- [[Transformation is 1-1 iff N(T) consists only of 0 vector]]
- [[Linear Map Between Vector Spaces With Same Finite Dimension Properties]]
- From Ex. 14, if T is linear and 1-1, then subset S is lin. ind. iff T(S) is lin ind.
- Theorem 2.6: Suppose basis of V is given by $v_{1},\dots,v_{n}$, for $w_{1},\dots,w_{n} \in W$,  there exists exactly one linear transformation T s.t T(v_i) = w_i for i = 1, ..., n
	- n vectors from W can be uniquely expressed as a linear transformation of a given vector from V's basis
	- Corollary: *Let V and W be vector spaces and V has a finite basis. If U, T define a linear transformation where for each vector in basis the transformations are equal, then U = T*
<!--SR:!2025-08-27,12,270-->

#linear-algebra
