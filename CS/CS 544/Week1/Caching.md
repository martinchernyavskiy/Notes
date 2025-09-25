## CPU and RAM Loading/Storing
?
- CPU has *registers* which are like variables built in it
- CPU clock oscillates billions of times per second
- For adding numbers in RAM, we need to load before adding and then storing them after
- *Latency*
- Loading a value from RAM takes about 60ns or 200 cycles
	- Slow but not long enough to switch to a different process
	- Time indicates latency, throughout shows how many bytes per second can be loaded

## Cache
?
- *Storing data in a temporary storage area to enable faster access to that data in the future*
- CPUs can have small memory built in for data accessed frequently
	- This decreases the latency it takes to read from RAM

## Cache Hierarchy
?
- Faster --> Slower
	- CPU registers
		- L1 cache
		- L2 cache
		- L3 cache
	- RAM
	- Storage Devices
	- Cloud Storage (network)

## Resource Tradeoffs
?
- OS caches file data in RAM
	- This uses memory
	- Avoids storage reads
- Browser caches recently visited page as a file
	- Uses storage space/reads
	- Avoids network transfers
- Python Dictionary caches return values in a dict
	- Uses memory space
	- Avoids repeated compute

## Manual Caching, Spark
?
```Spark
spark_df = ???? # usually not in memory
spark_df.cache() # put it in memory

spark_df.unpersists() # free up memory
```
- Stale data is deleted after expiration time
- SSD is large, so freshness is more important than space

## Cache Policies
?
- For browser visit, when you visit and the page isn't cached 
- When to load data to cache?
	- When read something, add it
	- Exception includes if it won't be read again
- When to evict data to a cache?
	- Random 
		- Select any entry randomly
	- FIFO
		- Evict whichever has been in cache the longest
	- LRU (least recently used)
		- Evict entry that has been used the least recently

## Demo
?
- 