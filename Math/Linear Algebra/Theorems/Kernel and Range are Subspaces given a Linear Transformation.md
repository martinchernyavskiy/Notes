### Theorem: If $T:V \to W$ is [[linear transformation]], then $N(T)$ is a [[subspace]] of $V$ and $R(T)$ is a [[subspace]] of $W$
?
#### Proof: 
For $R(T)$:
a) Need $\vec{0_{W}} \in R(T) \to$ Need a $v \in  V$ s.t $T(V)=\vec{0_{W}}$. Since T is linear, $T(\vec{0_{V}}=\vec{0_{W}})$, so we choose $v=\vec{0_{V}}$
b) Need $w_{1},w_{2} \in R(T) \to w_{1}+w_{2} \in R(T)$.
$w_{1},w_{2}\in R(T) \to w_{1}=T(v_{1}),w_{2}=T(v_{2})$, for some $v_{1},v_{2} \in V$
$\to w_{1}+w_{2} = T(v_{1})+T(v_{2})$
$\to w_{1}+w_{2} = T(v_{1}+v_{2})$
$\to w_{1}+w_{2} = R(T)$
c) Need $cw_{1} \in R(T) \space \forall c\in R$

For N(T)

This completes the proof. $\square$

### Immediately follow:

#### 1.
#### 2.