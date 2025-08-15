### Theorem: If $\{u_{1},\dots,u_{k}\} \subset V$ is linearly dependent, then one $u_{j}$ can be expressed as a linear combination of the others
?
#### Proof:
If subset is linearly dependent, then $a_{1}u_{1}+\dots+a_{k}u_{k}=\vec{0}$ for $a_{1},\dots,a_{k} \in R$ not all zero.
Assuming $a_{j}\neq 0$,
$$\begin{align}
\frac{1}{a_{j}}(a_{1}u_{1}+\dots+a_{k}u_{k}) =\frac{1}{a_{j}}\vec{0} \\
\frac{a_{1}}{a_{j}}u_{1}+\dots+\frac{a_{j}}{a_{j}}u_{j}+\dots+\frac{a_{k}}{u_{j}}u_{k}=\vec{0} \\
u_{j}=-\frac{a_{1}}{a_{j}}-\dots-\frac{a_{j-1}}{a_{j}}a_{j-1}-\frac{a_{j+1}}{a_{j}}u_{j+1}-\dots-\frac{a_{k}}{a_{j}}u_{k}
\end{align}
$$
This completes the proof. $\square$
<!--SR:!2025-10-14,60,310-->