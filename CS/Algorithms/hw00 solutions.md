
1st Problem, ascending order of growth rate:

logarithmic < polylogarithmic < polynomial < quasi-polynomial < exponential.

f5 < f6 < f3 < f2 < f7 < f1 < f4 < f8

![[Pasted image 20250903113916.png]]


2nd problem:
Euclidean algorithm by subtraction

a and b are positive non-zero values such that:
gcd(a,b) = d = gcd(b,a)
gcd(a, b) = gcd(a, b-a)

A correct algorithm preserves GCD and terminates at the base case

Algorithm 1:

Valid base case, gcd(a,a) = a,

since gcd(a, b) = gcd(a, b-a), second if statement for where a < b is a correct recursive step

since gcd(a, b) = gcd (b, a) = gcd(b, a-b) = gcd (a-b, b), else statement is the correct recursive step for when a < b 

*the algorithm correctly terminates at the base case and both a and b approach closer and become one value at the base case*

Algorithm 2:

This algorithm doesn't correctly compute gcd since it fails to consider the case where inputs were already equal, thus leading to an infinite recursion.

When the first check happens, for a=b, the else statement is executed and b is subtracted by a.
The next conditional block then results to false and thus triggers an else statement that recursively continues either subtracting b from a given a > b or a from b given b >= a 

counterexample any a=b

Algorithm 3:

in the case where a < b, the gcd(a, b) = gcd(b-a, b) does hold, however it doesn't guarantee that the arguments b-a and a get closer together to a single value. A counterexample could be (6,10)

Algorithm 4:

correct base and a < b recursive steps, however it's not true that gcd(a, b) = gcd (b, ab) and thus the algorithm is invalid.

Since (ab) is a multiple of b, the answer always results in b

Can introduce another counterexample

Algorithm 5:

correct base case since we're trying to achieve gcd(a, a) = a

correct recursive step for a < b, thus decreasing b by a value, moving them closer together



3rd problem:

4th:

Done.