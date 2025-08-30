### Theorem: If B is mxm matrix and A is mxn matrix, then rank(BA) = rank(A)
?
#### Proof: 
rank(BA) = rank(L_BA)
		= dim(R(L_BA))
R(L_BA) = {L_BA(v) | v in Rn }, subset of Rm
		= {(BA)(v) | v in Rn}
		= {B(A(v)) | V in Rn}
		= L_B( {A(V) | v in Rn} )
		where the set is R(L_A)
Since B is invertible --> L_B : Rm --> Rm
Define another map Li_B : R(L_A) --> L_B(R(L_A))
This map is invertible by invertibility of B and thus rank(A) = rank (BA)

This completes the proof. $\square$
