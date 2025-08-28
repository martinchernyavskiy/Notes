
## Definition
?
*Given vector spaces V, W, we define a vector space:
$\mathcal{L}(V,W)=\{ T: V \to W \}$* *which is the set of all linear maps from V to W*
<!--SR:!2025-09-02,14,290-->

## Additional Definitions
?
From [[Composition of Linear Transformations is Linear]], we define Matrix Multiplication:
- Given $A \in M_{m \times n}$ and $B \in M_{n \times p}$ define:
	$(AB)_{ij}= \sum_{k=1}^{n}A_{ik}B_{kj}$
	Alternatively,
	AB = $A(\bar{b_{1}},\dots,\bar{b_{p}})$ = $(A\bar{b_{1}},\dots,A\bar{b_{p}})$
- *Kronecker delta $\delta_{ij}$ = 1 where i=j and 0 everywhere else*. Identity matrix is given by $(I_{n})_{ij} = \delta_{ij}$
- $A^k = A^{k-1}A$, $A^0=I_{n}$
<!--SR:!2025-08-28,9,250-->

## Examples
?
- $S \in \mathcal{L}(X, Y)$ and $T \in \mathcal{L}(Y, Z)$
	$X \xrightarrow{S} Y \xrightarrow{T} Z$ can define a composition
	$T\circ S: X \to Z$
	$x \to T(S(v))$
- $(AB)^t = B^tA^t$
<!--SR:!2025-08-29,10,270-->

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
- [[Matrix Column Relations]]
- [[Left-Multiplication Transformation Properties]]
<!--SR:!2025-09-03,15,290-->


#linear-algebra


#### 1. Analyzing the Left Side: (AB)C

First, we find the entry in the i-th row and k-th column of the product AB.

$$(AB)_{ik} = \sum_{j=1}^{n} A_{ij}B_{jk}$$Next, we use this result to find the entry in the $i$-th row and $l$-th column of $(AB)C$.$$\big((AB)C\big)_{il} = \sum_{k=1}^{p} (AB)_{ik} C_{kl}$$Now, we substitute the expression for $(AB)_{ik}$ into this equation:$$\big((AB)C\big)_{il} = \sum_{k=1}^{p} \left( \sum_{j=1}^{n} A_{ij}B_{jk} \right) C_{kl}$$

---

#### 2. Analyzing the Right Side: A(BC)

First, we find the entry in the j-th row and l-th column of the product BC.

$$(BC)_{jl} = \sum_{k=1}^{p} B_{jk}C_{kl}$$Next, we use this result to find the entry in the $i$-th row and $l$-th column of $A(BC)$.$$\big(A(BC)\big)_{il} = \sum_{j=1}^{n} A_{ij} (BC)_{jl}$$Now, we substitute the expression for $(BC)_{jl}$ into this equation:$$

\big(A(BC)\big)_{il} = \sum_{j=1}^{n} A_{ij} \left( \sum_{k=1}^{p} B_{jk}C_{kl} \right)$$

---

#### 3. Comparing the Results

Let's look at the final expressions for the general entry of each side.

- **Left Side:** ((AB)C)il​=∑k=1p​(∑j=1n​Aij​Bjk​)Ckl​=∑k=1p​∑j=1n​Aij​Bjk​Ckl​
    
- **Right Side:** (A(BC))il​=∑j=1n​Aij​(∑k=1p​Bjk​Ckl​)=∑j=1n​∑k=1p​Aij​Bjk​Ckl​
    

Because these are finite sums, we can exchange the order of summation. Therefore:

k=1∑p​j=1∑n​Aij​Bjk​Ckl​=j=1∑n​k=1∑p​Aij​Bjk​Ckl​

The entry in the i-th row and l-th column is the same for both (AB)C and A(BC). Since this holds true for any arbitrary entry, the matrices must be equal.

This completes the proof that matrix multiplication is **associative**. ✅