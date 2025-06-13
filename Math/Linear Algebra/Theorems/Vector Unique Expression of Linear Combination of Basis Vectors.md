### Theorem: If $\beta \subset V$ is a basis, then $\forall v \in V$ can be expressed in a unique way as an element of $Span(\beta)$
?
#### Proof:
Let $u \in V$, $u=a_{1}v_{1}+\dots+a_{k}v_{k}$ for $u_{1},\dots,u_{k} \in \beta$
Suppose $u$ can also be expressed as $u=b_{1}u_{1}+\dots+b_{k}u_{k}+b_{k+1}+\dots+b_{l}u_{l}$
Then,
$$
\begin{array}{l}
u-u=\vec{0}  \\
(a_{1}u_{1}+\dots+a_{k}u_{k})-(b_{1}u_{1}+b_{l}u_{l}) = \vec{0} \\
(a_{1}-b_{1})u_{1}+\dots+(a_{k}-b_{k})u_{k}-b_{k+1}u_{k+1}-\dots-b_{l}u_{l}
\end{array}
$$
By linear independence of $\beta$, all coefficients are 0, thus $a_{1}=b_{1},\dots a_{k}=b_{k},b_{k+1}=0,\dots,b_{l}=0$
Therefore, every vector in V can be expressed in a unique way as element of $Span(\beta)$
This completes the proof. $\square$
<!--SR:!2025-06-27,14,290-->
