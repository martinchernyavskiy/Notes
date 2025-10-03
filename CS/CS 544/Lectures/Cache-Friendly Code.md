## CPU L1-L3
?
- *Granularity*
	- If process reads 1 byte and misses, how much data should CPU bring into cache?
		- If too little, we have more misses
		- If too much, wasteful load data to cache that might never be accessed
- *Cache Lines*: cache data units for CPU, granularity
	- Most common size of 64 bytes for modern CPUs
	- If we access element of the integer array and reading the following bytes of data
<!--SR:!2025-10-14,14,290-->


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
<!--SR:!2025-10-10,10,270-->

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
- Useful not just for numerical data but also for string since they are tighly packed contiguously in memory
- Uses WI mortgage loan csv file
```python
import pyarrow as pa
import pandas as pd
import pyarrow.csv
import pyarrow.compute as pc
import time

start_time = time.time()
t = pyarrow.csv.read_csv("hdma-wi-2021.csv") # creates a table from the csv file
end_time = time.time()
print((end_time-start_time) * 1000 + "ms") # about 431 ms

start_time2 = time.time()
dt = t.to_pandas(t) # converting pyarrow table into pandas dataframe
end_time2 = time.time()
print((end_time2-start_time2) * 1000 + "ms") # takes about 242 ms

pc.utf8_lower(t["lei"]).to_pandas()
t["income"]

pc.mean(t["income"].drop_null().as_py())
```
- PyArrow table has some columns that are integers, strings, etc.
	- CSV has strings only, but PyArrow has schema inference which automatically converts any string that looks like an integer to an integer type
	- Making such calculation is preferred in a cache-friendly layout
	- If we were to convert from the csv to pandas dataframe directly, the time it takes is quite slow since it's dominated by that schema inference
	- *PyArrow is more efficient but Pandas has more features. Converting from PyArrow to pandas is generally much faster*
- Pandas substitutes missing data in columns by NaN (double). SInce there is no NaN for integers, it's going to convert that to float unnecessarily
	- Since PyArrow has validity bitmap, it allows for integer operations which is faster than float operations
<!--SR:!2025-10-07,4,281-->

## Virtual Address Spaces
?
- Each process that runs a program has its own *virtual address space*, (where its locations (*pages*) are usually 4KB)
- Same virtual address refers to different memory in different processes
- Regular process *can't* directly access physical memory or other address spaces
	- Helps with isolation so that no process can interfere with each others' data
- Address spaces are sparse and have a lot of holes (data that exists in virtual address spaces are called *pages*)
	- Virtual address spaces are usually of much larger N than M of the physical addresses (these refer to number of pages)
	- Contiguous virtual address spaces may not be contiguous in physical memory addresses
<!--SR:!2025-10-04,4,278-->

## What goes in an address space?
?
- Code, stack and heap go on virtual address spaces (code and heap not contiguous)
- Some packages like numpy have code in C and this also goes on virtual address spaces
	- Uses instruction pointer (cpu attaches to one at and runs code by executing instructions and advancing the instruction pointer)
<!--SR:!2025-10-04,4,278-->

## OS Page Cache
?
- mmap (Memory Map) is a system call that:
	- Adds new regions to a virtual address space
		- Anonymous
			- import mmap
			- mm = mmap.mmap(-1, 4096 * 3)
			- -1 indicates anonymous mmap, number in that place is associated with open file
			- 4096 is 4KB which is roughly a page size and * 3 allocates exactly 3 pages to virtual memory that are mapped to physical addresses (contiguous in virtual address memory)
			- Usually done automatically by python to store objects on a heap
		- File-backed mmap
			- f = open("file.txt", mode="rb")
			- mm = mmap.mmap(f.fileno(), 0, access=mmap.ACCESS_READ)
				- fileno associates a file with a number
				- 0 indicates to allocate pages for the whole thing
				- Access provides protection for the data
				- Allocates 4kb pages on a virtual memory associated with 4kb chunks on the disk
					- Doesn't use any memory or does any computationally heavy task like reading from storage
					- When a program requests the data by indexing into the given virtual address space, the OS automatically reads that piece of data from storage into memory to be read by you.
					- Data loaded for accesses to file-backed mmap regions are part of the *page cache* 
						- Could evict data from memory when under memory pressure, but the data is still stored on the disk

## Swap Space
?
- Can we evict anonymous mmap from memory?
	- Usually can't, but can setup a system that permits it
		- Create a space (swap file) to which OS can evict data from anonymous mappings (so memory data is evicted to storage which is relatively slow)

## Demo (PyArrow + Docker), mmap
?
- docker run -p 301:300 -m 512mb demo
-  Generates a much bigger file than can be fit in memory with numbers from 1 to a million in each
```python
import pyarrow as pa
import pyarrow.compute as pc
import mmap

# Portion of a table with 3 columns
batch = pa.RecordBatch.from_arrays([range(1,1_000_000),
                                    range(1,1_000_000),
                                    range(1,1_000_000)],
                                   names=["x", "y", "z"])
print(batch.nbytes / 1024**2) # occupies around 23 mb of data

# Writes batch into a file 50 times >1 GB total which is storage data
with pa.ipc.new_file("test.arrow", schema=batch.schema) as f:
    for i in range(50):
        f.write_batch(batch)

# reads the 1GB file into a table, exceeds 512 mb cap and crashes container
with. pa.ipc.open_file("test.arrow") as f:
	t = f.read_all()
	
with open("test.arrow", "rb") as f:
	print(f.fileno())
	mm = mmap.mmap(f.fileno(), 0, access=ACCESS_READ)
	
	
## mm is basically an array of bytes and reading from it
with. pa.ipc.open_file(mm) as f:
	t = f.read_all() 
	
pc.sum(t["x"]) # brings in data from disk and automatically evicts already used data to not exceed memory
```
- ls /proc/