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