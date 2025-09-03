
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

Valid base case, 

Algorithm 2:

This algorithm doesn't correctly compute gcd since it fails to consider the case where inputs were already equal, thus leading to an infinite recursion.

When the first check happens, for a=b 

Algorithm 3:

Algorithm 4:

Algorithm 5:

3rd problem:

4th:

Done.