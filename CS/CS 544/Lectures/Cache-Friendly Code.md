## CPU L1-L3
?
- *Granularity*
	- If process reads 1 byte and misses, how much data should CPU bring into cache?
		- If too little, we have more misses
		- If too much, wasteful load data to cache that might never be accessed
- Cache Lines: cache data units for CPU, granularity
	- Most common size of 64 bytes for modern CPUs
	- If we access element of the integer array and reading the following bytes of data (granularity)


## Cache Lines and Misses
?
- As K step gets larger, we skip over more elements in the array, the cache line is given by the K value (end of plateau) times size of data (int32 in the class example), so 64 bytes
- *Matrices*
	- Logically they are 2-dimensional
	- Physically each row in arranged along a 1-dimension in 
## PyArrow
- Provides cache friendly layouts

## Demo
?
```
```

## OS Page Cache


## 