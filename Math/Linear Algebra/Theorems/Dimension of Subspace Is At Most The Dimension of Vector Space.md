### Theorem: Let W be a subspace of V. If V is finite dimensional, then $dimW\leq dimV$ with $dimW=dimV$ iff $W=V$
?
#### Proof:
Suppose $dimV=n$, then let $\beta_{V} = \{ u_{1},\dots,u_{n} \}$ be a basis for V.
Let $\mathcal{U} = \{ w_{1},\dots,w_{k} \} \subset W$ be a linearly independent subset of W.
By Replacement Theorem, ($S=\beta_{V},U=\mathcal{U} \to k\leq n$)
.
With this observation, we can construct a basis of W, recursively.
- If $W = \{ \vec{0_{V}} \}$, then done.
Otherwise, $w_{1} \neq \vec{0_{V}}$ in $W$
- If $W = Span(\{ w_{1} \})$, then done.
Otherwise, choose $w_{2}$ not in $Span(\{ w_{1} \})$
Note, $\{ w_{1},w_{2} \}$ is linearly independent
- If $W=Span(\{ w_{1},w_{2} \})$, done.
Otherwise, choose $w_{3}$ not in $Span({w_{1},w_{2}})$
$\{ w_{1},w_{2},w_{3} \}$ is linearly independent.
This process must stop at some
$\{ w_{1},\dots,w_{k} \}$ is linearly independent such that $W = Span(\{ w_{1},\dots, w_{k} \})$
By Replacement Theorem, $k\leq n$. Thus we have a linearly independent subset of W that spans it that has less than or equal to number of elements to the basis of V.
This completes the proof. $\square$
<!--SR:!2025-08-26,11,270-->
