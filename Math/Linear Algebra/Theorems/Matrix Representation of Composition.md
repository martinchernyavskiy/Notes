### Theorem: $[T \circ S]_{\alpha}^\gamma = [T]_{\beta}^\gamma [S]_{\alpha}^\beta$
?
#### Proof:
$\alpha = \{ (x_{1},\dots,x_{n}) \}$
$[T \circ S]_{\alpha}^\gamma=([T \circ S(x_{1})]_{\gamma} \dots[T \circ S(x_{n})]_{\gamma})$
$= ([(T(S(x_{1}))]_{\gamma}\dots[(T(S(x_{n}))]_{\gamma})$
By [[Matrix Representation Relation]],
$= ([T]_{\beta}^\gamma[S(x_{1})]_{\beta} \dots [T]_{\beta}^\gamma [S(x_{n})]_{\beta})$
$= [T]_{\beta}^\gamma[S(x_{1})]_{\beta}\dots[S(x_{n})]_{\beta}$
$=[T]_{\beta}^\gamma[S]_{\alpha}^\beta$
This completes the proof. $\square$
#### Example Showcase:
$A \in M_{m \times n} \to L_{A}:\mathbb{R}^n \to \mathbb{R}^m$
$B \in M_{p \times m} \to L_{B}: \mathbb{R}^m \to \mathbb{R}^p$
$[L_{B} \circ L_{A}]_{\alpha}^\gamma =[L_{B}]_{\beta}^\gamma[L_{A}]_{\alpha}^\beta = BA = [L_{BA}]_{\alpha}^\gamma$
$L_{B} \circ L_{A} = L_{BA}$
<!--SR:!2025-08-19,4,270-->
