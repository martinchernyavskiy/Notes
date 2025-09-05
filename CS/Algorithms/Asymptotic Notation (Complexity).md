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


Algorithm 1:

Argue that 1 is correct by induction a+b 

base case: gcd(1, 1) --> 1 for a+b smallest = 2 

inductive hypothesis: for a+b <= n the algorithm correctly 

inductive step: a+b = n+1

case 1: a=b

case 2: a< b the algorithm correct returns gcd(a, b-a) but we know by fact one that this equals to gcd(a, b)

case 3: is similar for a> b 



Algorithm 2: is not correct, gcd(4,4) will do gcd(4,0 ) forever

Algorithm 3: 

Algorithm 4:

counter examples are enough

Algorithm 5: correct

Lemma (intuition) --> gcd(a,b) = gcd(b, ab+a)

if y divides b and a(b+1) then u must divide a because b and b+1 cannot share any common factors

Formal proof:

by induction: induct on the first argument (a)

base case: a = 1, then gcd(1,b) follows from algorithm 1

inductive hypothesis: we induct on the first argument and assume the algorithm correctly returns gcd(a,b) for all a <= n

inductive step: a = n+1:

If a < b, it will return gcd(b-a, a) correct by fact 1

if a > b, then returns gcd(b. a(b+1) correctly by hypothesis and by lemma this is gcd of a, b