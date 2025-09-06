	way of measuring runtime against size of input.   ` 

## Properties
-  All functions match positive integers to positive real numbers


### Definition
- Big O notation: f = O(g(n)) if *there exists* positive c and n such that f(n) <= cg(n) for all n > N
- lim (f(n)) / g(n) = c --> f = O(g(n))

- Small o-notation: f = o(g(n)) if for *every* c there exists N such that f(n) <= cg(n) for all n >= N
- Omega notation: f = $\Omega(g(n))$ if there exists c and N such that cg(n) <= f(n) for all n >= N
- f = $\omega(g(n))$ if for all c, there exists n such that cg(n) <= f(n) for all n >= N
- f = O(g(n)) and g(n) = $\Omega(f(n))$
- f = o(g(n)) iff g(n) = $\omega(f(n))$

- $f = \Theta (g(n))$ if f = big o and omega of g(n)
