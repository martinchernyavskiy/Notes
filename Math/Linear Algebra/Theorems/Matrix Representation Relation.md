### Theorem: For all $v \in V, [T(v)]_{\gamma}=[T]_{\beta}^\gamma[v]_{\beta}$, where T acts like a matrix multiplication
?
#### Proof:
$\beta = \{  v_{1},\dots,v_{n} \}, \gamma = \{ w_{1},\dots,w_{m} \}$
$$
\begin{align}
[T(v)]_{\gamma} &= [T(a_{1}v_{1}+\dots+a_{n}v_{n})]_{\gamma} \\
&=[a_{1}T(v_{1})+\dots+a_{n}T(v_{n})]_{\gamma} \\
&= a_{1}[T(v_{1})]_{\gamma}+\dots a_{n}[T(v_{n})]_{\gamma} \\
&= ([T(v_{1})]_{\gamma}\dots[T(v_{n})]_{\gamma})\begin{pmatrix}
a_{1} \\
\vdots  \\
a_{n}
\end{pmatrix} \\
&= [T]_{\beta}^\gamma [v]_{\beta}
\end{align}
$$
Since T and and $[]_{\gamma}$ are linear transformations
.
In other words, all coordinate expressions of images of T can be expressed as a matrix multiplication of matrix representation of T and coordinate expression of the vector.x
This completes the proof. $\square$
<!--SR:!2025-08-19,4,270-->