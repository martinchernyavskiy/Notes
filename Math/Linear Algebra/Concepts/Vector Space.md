## Definition
*A vector space is a set of V, equipped with two operations: addition and scalar multiplication s.t the following 8 properties hold:*

## Properties / Axioms
?
1. $u + v = v + u$
2. $u + (v+w) = (u+v) + w$
3. $\exists$ 0 s.t u + 0 = u
4. $\exists$ w s.t u + w = 0
5. $1v = v$
6. $(ab)v = a(bv)$
7. $a(u+v) = au + av$
8. $(a+b)v = av + bv$
<!--SR:!2025-06-27,14,296-->

## ## Examples
?
- $\mathbb{R}$
	$a, b \in \mathbb{R}, \quad a + b \in \mathbb{R}, \quad c a \in \mathbb{R}$
.
- $\mathbb{R^n}$, same as above but add/multiply each tuple
.
- **$C^0(\mathbb{R})$** — continuous functions
	$(f+g)(x) = f(x) + g(x), \quad (c f)(x) = c f(x)$
‎.
- **$C^1(\mathbb{R})$** — continuous differentiable functions
  Same as above.
‎.
- **$\mathbb{M}_{m \times n}$** — set of m by n [[Matrix (Matrices)]]
	with component-wise addition and scalar multiplication.
	0 vector is matrix with all 0 entries
‎.
- **$\mathcal{F}(S)$** where $S$ is non-empty: $f : S \to \mathbb{R}$
	$(f+g)(s) = f(s) + g(s),\quad(c f)(s) = c f(s)$
	$\vec{0}$ is a function that maps all s to 0
‎.
- **$\mathcal{F}(\mathbb{N})$** — functions $\sigma : \mathbb{N} \to \mathbb{R}$
‎.
- **$V = \{ \{ a_n \} \}$** — set of sequences
	$\{ a_n \} + \{ b_n \} = \{ a_n + b_n \}, \quad c \{ a_n \} = \{ c a_n \}$
.
- $P_{n}$ = {[[polynomial]]s f(x) of degree at most n}
	$P(x) + G(x) = (a_{n}+b_{n})x^n+\dots+(a_{0}+b_{0})$
	$cP(x) = ca_{n}x^n+\dots+ca_{0}$
	$\vec{0} = 0 = 0x^n+\dots+0x+0$
<!--SR:!2025-10-20,66,316-->


## Non-examples
?
- Consider $\mathbb{R}^2$ equipped with
	$(a_{1},a_{2})+(b_{1},b_{2}) = (a_{1}+b_{1}, a_{2}b_{2})$
	$c(a_{1},a_{2})=(ca_{1},a_{2})$
	8th property doesn't hold
<!--SR:!2025-10-12,58,316-->


## Theorems
- [[Elementary Properties of Vector Spaces]]


#linear-algebra