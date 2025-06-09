### Theorem: Suppose $\{u_{1},\dots,u_{k}\} \subset V$ is linearly dependent, there is a subset $\{u_{i1},\dots u_{il}\}$ that satisfies $Span(\{u_{i1},\dots u_{il}\})=Span(\{u_{1},\dots,u_{k}\})$
?
#### Proof:
By [[Linearly Dependent Subset Vector as Linear Combination of Others]], since $\{u_{1},\dots,u_{k}\}$ is linearly dependent, for some j,
$u_{j}=b_{1}v_{1}+\dots+b_{j-1}u_{j-1}+b_{j+1}u_{j+1}+\dots+b_{k}u_{k}$
We remove $u_{j}$ from the set.
**Claim:** $Span(\{u_{1},\dots,{u_{j}},\dots,u_{k}\})=Span(\{u_{1},\dots,\hat{u_{j}},\dots,u_{k}\})$
Given $a_{1}v_{1}+\dots+a_{j}v_{j}+\dots+a_{k}v_{k}$, need to show that this is in the Span without vector $u_{j}$
$$
\begin{array}{l} \\
a_{1}v_{1}+\dots+a_jv_{j}+\dots +a_{k}v_{k} \\
= a_{1}v_{1}+\dots+a_{j}(b_{1}v_{1}+\dots+b_{k}v_{k})+\dots+a_{k}v_{k} \\
= (a_{1}+a_{j}b_{1})u_{1}+\dots+(a_{k}+a_{j}b_{k})u_{k \\}
\end{array}
$$
Claim is verified.
If $\{u_{1},\dots,u_{j-1},u_{j+1},\dots,u_{k}\}$ is linearly independent, we stop, otherwise find another $u_{i}$ to remove.
Eventually this has to stop.
<!--SR:!2025-06-13,4,270-->

This completes the proof. $\square$
