## CPU L1-L3
?
- *Granularity*
	- If process reads 1 byte and misses, how much data should CPU bring into cache?
		- If too little, we have more misses
		- If too much, wasteful load data to cache that might never be accessed
- *Cache Lines*: cache data units for CPU, granularity
	- Most common size of 64 bytes for modern CPUs
	- If we access element of the integer array and reading the following bytes of data 
<!--SR:!2025-09-30,4,270-->


## Cache Lines and Misses
?
- As K step gets larger, we skip over more elements in the array, the cache line is given by the K value (end of plateau) times size of data (int32 in the class example), so 64 bytes
	- For k 1 to 16, hardly any difference is noticeable for the runtime of the program, that is because the runtime is dominated by the memory access to the array and we're reading cache lines one by one for this k interval
		- For the case when k = 32 or any further square, we're skipping over a cache line and accessing only every second one and so on.
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

## Demo (NumPy)
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
<!--SR:!2025-10-10,10,270-->

## Demo(PyArrow)
?
- Uses WI mortgage loan csv file
```python
import pyarrow as pa
import pandas as pd
import pyarrow.csv
import pyarrow.compute as pc
import time

start_time = time.time()
t = pyarrow.csv.read_csv("hdma-wi-2021.csv")
end_time = time.time()
print((end_time-start_time) * 1000 + "ms")

start_time2 = time.time()
dt = t.to_pandas(t)
end_time2 = time.time()
print((start_time2-end_time2) * 1000 + "ms")

pc.utf8_lower(t["lei"].to_lower())
t["income"]

pc.mean(t["income"].drop_null().as_py())
```
- Using PyArrow schema is faster for parsing through csv
- Pandas substitutes missing data in columns by NaN (double)
## Virtual Address Spaces
?
- Each process that runs a program has its own *virtual address space*, (also called *pages* which are usually 4KB)
- Same virtual address refers to different memory in different processes
- Regular process *can't* directly access physical memory or other address spaces
	- Address spaces can have holes (data that exists in virtual address spaces are called *pages*)
	- Physical memory for process doesn't need to be contiguous

## What goes in an address space?
?
- Code, stack and heap go on virtual address spaces (code and heap not contiguous)
- Some packages like numpy have code in C and this also goes on virtual address spaces
	- Uses instruction pointer (cpu attaches to one at and runs code by executing instructions and advancing the instruction pointer)

## OS Page Cache
?
- mmap (Memory Map)
	- Adds new regions to a virtual address space
		- Anonymous
			- import mmap
			- mm = mmap.mmap(-1, 4096*3)
			- -1 indicates anonymois mmap
		- Backed by a file
			- f = open("file.txt", mode="rb")
			- mm = mmap.mmap(f.fileno(), 0, access=mmap.ACCESS_READ)
				- 0 means all
				- automatically reads data from disk and loads it into a physical memory when we read data for the virtual address spaces

## Demo (PyArrow + Docker), mmap
?
- docker run -p 301:300 -m 512mb demo
-  
```python
import pyarrow as pa
import pyarrow.compute as pc

batch = pa.RecordBatch.from_arrays([range(1,1_000_000),
                                    range(1,1_000_000),
                                    range(1,1_000_000)],
                                   names=["x", "y", "z"])
print(batch.nbytes / 1024**2)

with pa.ipc.new_file("test.arrow", schema=batch.schema) as f:
    for i in range(50):
        f.write_batch(batch)

```
