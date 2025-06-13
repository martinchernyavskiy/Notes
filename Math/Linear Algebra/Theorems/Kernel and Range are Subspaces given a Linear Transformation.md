### Theorem: If $T:V \to W$ is [[linear transformation]], then $N(T)$ is a [[subspace]] of $V$ and $R(T)$ is a [[subspace]] of $W$
?
#### Proof: 
For $R(T)$:
a) Need $\vec{0_{W}} \in R(T) \to$ Need a $v \in  V$ s.t $T(v)=\vec{0_{W}}$. Since T is linear, $T(\vec{0_{V}})=\vec{0_{W}}$, so we choose $v=\vec{0_{V}}$
b) Need $w_{1},w_{2} \in R(T) \to w_{1}+w_{2} \in R(T)$.
$w_{1},w_{2}\in R(T) \to w_{1}=T(v_{1}),w_{2}=T(v_{2})$, for some $v_{1},v_{2} \in V$
$\to w_{1}+w_{2} = T(v_{1})+T(v_{2})$
$\to w_{1}+w_{2} = T(v_{1}+v_{2})$
$\to w_{1}+w_{2} \in R(T)$
c) Need $cw_{1} \in R(T) \space \forall c\in R$
$w_{1} \in R(T) \to w_{1}=T(v_{1})$
$cw_{1}=c(T(v_{1}))$
$cw_{1}=T(cv_{1})$
$cw_{1} \in R(T)$
.
For N(T)
a) Need $\vec{0_{V}} \in N(T) \to$ need $T(\vec{0_{V}})=\vec{0_{W}}$. Since T is linear, this is true by definition
b) Need $v_{1},v_{2} \in N(T) \to v_{1}+v_{2} \in N(T)$. Since $v_{1},v_{2} \in N(T)$, $T(v_{1}) = \vec{0_{W}},T(v_{2})=\vec{0_{W}}$
$T(v_{1})+T(v_{2})=\vec{0_{W}}+\vec{0_{W}}=\vec{0_{W}=T(v_{1}+v_{2})}$. So $v_{1}+v_{2} \in N(T)$
c) Need $v_{1} \in N(T) \to cv_{1} \in N(T)$
$v_{1} \in N(T) \to T(v_{1})=\vec{0_{W}}$
$T(cv_{1})=cT(v_{1})=c \vec{0_{W}}=\vec{0_{W}}$, hence $cv_{1} \in N(T)$
This completes the proof. $\square$
