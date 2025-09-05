## Properties
-  All functions match positive integers to positive real numbers


### Definition
- Big O notation: f = O(g(n)) if *there exists* positive c and n such that f(n) <= cg(n) for all n > N
- lim (f(n)) / g(n) = c --> f = O(g(n))

- Small o-notation: f = o(g(n)) if for *every* c there exists N such that f(n) <= cg(n)
- Omega notation: f = $\Omega(g(n))$ if there exists c and N such that cg(n) <= f(n) for all n >= N
- f = $\omega(g(n))$ if for all c, there exists n such that cg(n) <= f(n) for all n >= N
- f = O(g(n)) and g(n) = $\Omega(f(n))$
- f = o(g(n)) iff g(n) = $\omega(f(n))$

- $f = \Theta (g(n))$ if f = big o and omega of g(n)


Problem 1:

f5 < f6 < f3 < f2 < f7 <  f1 < f4 < f8

Problem 2:

### Claim 10^n  = O(log(n)^n-2)
- By definition or can see what big O each function is


Problem 2:

Algorithm 1: 

Partial correctness: Need to confirm that for all valid inputs, when the program terminates we receive the right output

Case a = b, then gcd(a, b) = gcd (a, a) and the algorithm returns the right output which is a

Case a > b = ...

...

Standard gcd implementation

Termination: Need to inductively prove that for the program terminates (induction on a decreasing quantity for each recursion call)

Algorithm 2:

Take a = b, then the algorithm executes infinitely since either of the inputs keep decreasing 