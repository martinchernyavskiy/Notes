
## Definitions
?
*Suppose $T:V \to W$ is linear.
Null Space (Kernel) of $T$ is:
$N(T)=\{ v \in V|T(v) = \vec{0_{W}} \} \subset V$
Range (Image) of $T$ is:
$R(T) = \{ T(v) | v \in V \} \subset W$*
<!--SR:!2025-06-17,4,270-->


## Additional Definitions
?
- $T:V \to W$ is onto if $R(T)=W$ or $\forall w \in W, \exists v \in V$ s.t $T(v)=w$
- $T:V \to W$ is 1-1 if
  $T(v_{1})=T(v_{2}) \to v_{1}=v_{2}$

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
<!--SR:!2025-06-16,3,250-->

## Theorems
- [[Kernel and Range are Subspaces given a Linear Transformation]]
- [[Dimension Theorem(Rank Nullity Theorem)]]
- [[Transformation is 1-1 iff N(T) consists only of 0 vector]]
- [[Linear Map Between Vector Spaces With Same Finite Dimension is a Bijection]]


#linear-algebra