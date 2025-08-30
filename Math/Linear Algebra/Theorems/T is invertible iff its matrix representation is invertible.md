### Theorem: Let V and W be finite-dimensional vector spaces with ordered bases beta and gamma. Let T: V --> W be linear. Then T is invertible iff $[T]_{\beta}^{\gamma}$ is invertible. Furthermore, $[T^-1]_{\gamma}^{\beta}=([T]_{\beta}^{\gamma})^-1$
#### Proof: 
Suppose that T is invertible. Then by [[For a invertible linear map, V is finite dimensional iff W is finite dimensional]], dimV = dimW. Let V be n-dimensional, then matrix representation of T is nxn matrix. 
Let T^-1 : W -- V be inverse of T and thus TT^-1 = Iw and T^-1T = Iv.
Then, $I_{n}=[I_{V}]_{\beta}=[T^-1T]_{\beta}=[T^-1]_{\gamma}^{\beta}[T]_{\beta}^{\gamma}$ , by [[Matrix Representation of Composition]]
Similarly, multiplying the two matrix representations in the opposite way results in In also. Thus, matrix representation of T is invertible and $[T^-1]_{\gamma}^{\beta}=([T]_{\beta}^{\gamma})^-1$
Now suppose that A is a matrix representation of T and it's invertible. Then there exists matrix B such that AB = BA = In. Since any linear transformation is defined by its effect on the basis vectors, then there must be a linear transformation U: W --> V for which its matrix representation is B. 
U is defined as U(wj) = linear combination of image basis vectors with coefficients from jth column of B. 
Now we need to show that U is inverse of T. 
$[UT]_{\beta}=[U]_{\gamma}^{\beta}[T]_{\beta}^{\gamma}$
This completes the proof. $\square$
