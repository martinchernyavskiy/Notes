## Software Categories
?
*Systems* : *Software for managing computer resources*
- *Analysis code* (run once, get result)
- *Applications* (long running / website)
- Systems (manage resources)
	- operating system is a backbone of analysis code
<!--SR:!2025-11-10,45,292-->

### Resource Categories
?
Computer:
- CPU, GPU for computing
- RAM for active memory
Resources:
- *Storage* (long-term data)
- *Network* (provides communication between computers)
	- Managed by Network Interface Card (*NIC*)
<!--SR:!2025-11-24,57,312-->

## Bid Data Systems
?
Servers whose datasets grow may run too slowly or not run at all given there is not enough memory.
- *Scale Up / Out* or *More efficient code*
- *Distributed* (cluster of machines)
- *Specialized* (GPUs)
<!--SR:!2025-09-30,16,292-->

## Compute
?
- Some computers use multiple CPUs and CPUs may have multiply *cores*.
- OS *schedules tasks* on cores
- Each core can execute instructions for one/two tasks at a time
	- Each instruction is written in machine code that CPU operates on
- The more cores available, the more tasks can be ran in *parallel*
<!--SR:!2025-11-05,40,290-->


## High-Language Translation
?
- High level code can either be *compiled* into machine code by a *compiler* which is a separate software or CPU runs an *interpreter* program that loops over code and runs it
- Another approach is for compiler to create *bytecode* and VM running on CPU will run the bytecode
- Python VM (*PVM*) runs bytecode after *python3* is executed which compiles python code into a bytecode file
	- This is similar to JVM that runs class bytecode files after compilation, however *JVM*'s bytecode is closer to machine code
<!--SR:!2025-11-06,41,290-->


## GPUs
?
- GPUs: graphical processing units which contrary to CPU that has few cores that are fast and independent, has many *cores that are slow, float-optimized, and coordinated.*
.
- *FLOPS*: floating-point operations per second, way of measuring performance of GPUs
- *Benchmark*: program for measuring performance
<!--SR:!2025-11-23,56,312-->

## RAM
?
- Randomly accessed : fast at accessing different locations efficiently
- *Byte addressable*
	- Each byte of data has its own address that the CPU can use to access it
- *Fast, volatile, small*
<!--SR:!2025-09-30,16,292-->

## Storage
?
- *HDDS* (Hard Disk Drivers)
	- Bits stored on spinning magnetized platter
	- Moving head reads/writes data
- *SSDs* (Solid State Disks)
	- Bits stored in charged cells
	- No moving parts (faster)
- *Block Devices*
- *Large, nonvolatile, slow*
### Metrics
- *Capacity*
	• how much data can be stored?
	• measured in bytes (for example, 500 GB)
- *Throughput*
	• how fast can data be read/written?
	• measure in bytes/second (for example, 200 MB/s)
	• throughput will depend on access pattern (for example,
	spinning disks have low throughput for random
	accesses)
- *Latency*
	• how long does it take to do one I/O (e.g., 10 ms)
<!--SR:!2025-11-04,39,290-->

## Network
?
- Clustered machines (*nodes*) utilize network communication
- *Topology*: layout of devices
### Metrics
- *Latency*: how long to send message between two points
- *Bandwidth / Throughput*: how many bits can be sent per second
<!--SR:!2025-11-03,38,290-->

## Deployment
?
- Running code somewhere, for example a *cloud VM*
- *Docker Containers*: lightweight alternative to virtual machines, allows for creation of cluster machine ecosystem in a single system
<!--SR:!2025-09-29,15,290-->