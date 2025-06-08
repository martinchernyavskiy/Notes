### Theorem: Let $u,v,w$ be elements of a [[vector space]] V. If $u+w$ = $v+w$, then $u=v$.
?
#### Proof:
We will use the 8 axioms of a Vector Space.
By (4) there is a $z\in V$ s.t $w+z = \vec{0}$
$$
\begin{aligned}
u & = u + \vec{0} \quad (3) \\
  & = u + (w + z) \\
  & = (u + w) + z \quad (2) \\
  & = (v + w) + z \quad (\text{hypoth.}) \\
  & = v + (w + z) \quad (2) \\
  & = v + \vec{0} \\
  & =  v\quad (3)
\end{aligned}
$$
This completes the proof. $\square$
### Immediately follow:
#### $0v = \vec{0}$
#### $\vec{0}$ is uniquely defined by (3)
#### For v, the w s.t $v+w=\vec{0}$ is unique. In fact, $w=-v \leftrightarrow w=-1(v)$

