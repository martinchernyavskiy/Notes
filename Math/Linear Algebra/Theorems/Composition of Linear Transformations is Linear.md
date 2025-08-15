### Theorem: $T \circ S$ is linear $(T \circ S \in \mathcal{L}(X,Z))$
?
#### Proof:
$(T \circ S)(x_{1}+cx_{2})=T(S(x_{1}+cx_{2}))$
$= T(S(x_{1})+cS(x_{2}))$ since S is linear
$= T(S(x_{1}))+cT(S(x_{2}))$ since T is linear
$= (T \circ S)(x_{1})+c(T \circ S)(x_{2})$
This completes the proof. $\square$
### Immediately follow:
#### 1. Suppose X,Y,Z are finite dimensional w/ bases:
$${\begin{array}{l}
\alpha = \{ x_{1},\dots,x_{n} \} \\
\beta = \{ y_{1}, \dots , y_{m} \} \\
\gamma = \{ z_{1},\dots , z_{p} \}
\end{array}}
$$
- #### How are $[S]_{\alpha}^\beta[T]_{\beta}^\gamma$ and $[T \circ S]_{\alpha}^\gamma$ related? Define matrix multiplication
<!--SR:!2025-08-19,4,270-->
