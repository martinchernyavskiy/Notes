## CPU L1-L3
?
- *Granularity*
	- If process reads 1 byte and misses, how much data should CPU bring into cache?
		- If too little, we have more misses
		- If too much, wasteful load data to cache that might never be accessed
- Cache Lines: cache data units for CPU, granularity
	- Most common size of 64 bytes for modern CPUs
	- If we access element of the integer array and reading the following bytes of data (granularity)
<!--SR:!2025-09-30,4,270-->


## Cache Lines and Misses
?
- As K step gets larger, we skip over more elements in the array, the cache line is given by the K value (end of plateau) times size of data (int32 in the class example), so 64 bytes
- *Matrices*
	- Logically they are 2-dimensional
	- Physically each row in arranged along a 1-dimension in virtual address space
		- Fast for summing over rows, slow for summing over columns
- *Solution with NumPy*
	- Transpose doesn't move or copy data
		- Putting column data in rows and transposing provides fast column sum
- The layout where data is contiguous is most cache friendly since we have less misses and only need to read one cache line
## PyArrow
?
- Provides cache friendly layouts (data structures)
	- String array
		- Length
		- Null count
		- Validity Bitmap
			- For byte 0 contains 1 bits to denote that string data exists and 0 for null
			- Contains 63 bytes of padding
		- Offsets Buffer: list of indices that point to the start of each string in value buffer
		- Value buffer: contains non-null strings contiguously
			- Data is packed into fewest possible cache lines
<!--SR:!2025-09-30,4,270-->

## Demo
?
- Run a jupyterlab on a docker container and connect to it through local browser
```python
import numpy as np
import time

A = np.random.randint(0, 10, (1_000_000, 8))
print(A.dtype)
print(A.shape)

start = time.time()
result = A[:, 0].sum() # Sums every int64 number in the 0th column
end = time.time()
print((start-end) * 1000 + "ms")

B = A.T.copy().T # Same data, but different memory layout, allows for much faster column sum per what we described about memory layouts and cache lines
start = time.time()
result = B[:, 0].sum() # Sums every int64 number in the 0th column
end = time.time()
print((start-end) * 1000 + "ms")
```
<!--SR:!2025-09-30,4,270-->

## OS Page Cache


## 