### Theorem: Let V and W be vector spaces, and let T: V --> W be linear and invertible, that is there is a T^-1 : W --> V s.t T(T^-1) = Iw and T^-1(T) = Iv. Then T^-1 is linear
 ?
#### Proof: 
By invertibility of T, it must be both one-to-one and onto. Then let y1,y2 in W and c in field F and there exist unique vectors x1 and x2 such that T(x1) = y1 and T(x2) = y2. Thus, x1 = T^-1(y1) and x^2 = T^-1(y2).
So, T^-1(cy1+y2) = T^-1(cT(x1)+T(x2)) = T^-1(T(cx1+x2)) = cx1+x2 = cT^-1(y1) + T^-1(y2)
This completes the proof. $\square$

### Immediately follow:

#### 1.
#### 2.