
## Change of Coordinates
?
*Given two different finite bases for V, how are coordinate expressions for its vectors related?*
## Properties / Axioms
- Let $\beta \text{ and } \beta^{'}$ be such two bases. Then $[v]_{\beta^{'}} = [I_{V}(v)]_{\beta^{'}} = [I_{V}]_{\beta}^{\beta^{'}}[v]_{\beta}$ 

## Example
?
- Let V = P1, beta = 1, x, beta2 = 1+x, 1-x
- $[I_{V}]_{\beta}^{\beta^{'}}$ equals to matrix where columns are coordinate expressions of image of the domain basis vectors in terms of basis vectors of codomain basis.

## Change of Bases
?
*Given a map between V and W who have 2 different bases for each respectively, how are matrix representations of the map differ with respect to two standard bases and 2 other ones?*

## Properties / Axioms
?
$$
\begin{aligned}
 & \left[T\right]_{\beta^{\prime}}^{\gamma^{\prime}}=[I_W\circ T\circ I_V]_{\beta^{\prime}}^{\gamma^{\prime}} \\
 & =[I_W]_\gamma^{\gamma^{\prime}}[T\circ I_V]_{\beta^{\prime}}^\gamma \\
 & =[I_W]_\gamma^{\gamma^{\prime}}[T]_\beta^\gamma[I_V]_{\beta^{\prime}}^\beta \\
 & 
\begin{bmatrix}
T
\end{bmatrix}_{\beta^{\prime}}^{\gamma^{\prime}}=[I_W]_\gamma^{\gamma^{\prime}}[T]_\beta^\gamma[I_V]_{\beta^{\prime}}^\beta
\end{aligned}
$$
- If W = V and their bases are equal also, then:
$$
\begin{aligned}
\begin{bmatrix}
T
\end{bmatrix}_{\beta^{\prime}}^{\beta^{\prime}} & =
\begin{bmatrix}
I_V
\end{bmatrix}_\beta^{\beta^{\prime}}
\begin{bmatrix}
T
\end{bmatrix}_\beta^\beta
\begin{bmatrix}
I_V
\end{bmatrix}_{\beta^{\prime}}^\beta \\
 & =Q^{-1}[T]_\beta^\beta Q, \\
 & \mathrm{where~}Q=
\begin{bmatrix}
I_V
\end{bmatrix}_{\beta^{\prime}}^\beta
\end{aligned}
$$

## Similar Matrix
?
*Two square matrices are similar if there exists another square matrix such that B = Q^-1 A Q*
## Example


## Theorems
- [[Inverse of change of coordinate matrix]]



#linear-algebra