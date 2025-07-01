- Yingfei Xiong


### Programming Languages
- Why are there so many different type of languages? 
	Because it makes programming easier
	- Machine Code
	- Assembly Language
	- High-level programming languages (Imperative programming languages)

### Functional Programming Languages
- Functional and logical programming languages are a separate family
- Describe goal $\to$ computer finds the right computation
- Program: input $\to$ output
- Functional programming language takes the mathematics form of functions
- f(a, b) = a+b is supporte, but f(a+1, b+1) = a+b-2 has a limited support though pattern matching
- Families:
  - Lisp family (standard lisp, scheme, racket)
  - ML family (ML, Ocaml, F#)
  - Haskell

### Example of Functional Programming
```Haskell
quicksort[] = []
	quicksort(p:xs) = (quicksort lesser) ++ [p] ++ (quicksort greater)
	where
		lesser = filter (< p) xs
		greater = filter (>= p) xs

``` 

```Haskell
main = do
	let file = "abc.txt"
	contnets <- readFile file
	putStrLn contents
```


### Modern Features of Functional Programming
- High-Order Functions (MapReduce divides bigger task into smaller task, two standard functions in standard function map (+1) [1,2,3])
- Algebraic data Types
- Structural Type System
- Functional Data Structures