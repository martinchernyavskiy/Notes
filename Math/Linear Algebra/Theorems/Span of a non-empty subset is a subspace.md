### Theorem: For any non-empty subset $S \subset V$, Span(S) is a subspace of V
?
#### Proof:
$Span(S) = \{a_{1}u_{1}+\dots a_{k}u_{k}|a_{1},\dots,a_{k} \in R, u_{1},\dots u_{k} \in S\}$.
a) Choose $u \in S$, then $0u \in Span(S)$ since this is a linear combination of vector u in S, so $\vec{0} \in Span(S) \quad \checkmark$
b) Need $u,v \in Span(S) \to u+v \in Span(S)$
Let $u = a_{1}u_{1}+\dots+a_{k}u_{k}$, $v=b_{1}v_{1}+\dots+b_{k}u_{k}$
Then $u+v=(a_{1}+b_{1})u_{1}+\dots+(a_{k}+b_{k})u_{k}$,since this is a linear combination of u in S, $u+v \in Span(S) \quad \checkmark$
c) Need $u \in Span(S) \to cu \in Span(S)$
$u = a_{1}u_{1}+\dots+a_{k}u_{k}$
$cu = (ca_{1})u_{1}+\dots+(ca_{k})u_{k}$ since this is a linear combination of u in S, $cu \in Span(S) \quad \checkmark$
This completes the proof. $\square$
<!--SR:!2025-06-13,4,270-->