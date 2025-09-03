## Software Categories
?
*Systems* : *Software for managing computer resources*
- *Analysis code* (run once, get result)
- *Applications* (long running / website)
- Systems (manage resources)
	- operating system is a backbone of analysis code
### Resource Categories
?
Computer:
- CPU, GPU for computing
- RAM for active memory
Resources:
- *Storage* (long-term data)
- *Network* (provides communication between computers)
	- Managed by Network Interface Card (*NIC*)

## Bid Data Systems
?
Servers whose datasets grow may run too slowly or not run at all given there is not enough memory.
- *Scale Up / Out* or *More efficient code*
- *Distributed* (cluster of machines)
- *Specialized* (GPUs)

## Compute
?
- Some computers use multiple CPUs and CPUs may have multiply *cores*.
- OS *schedules tasks* on cores
- Each core can execute instructions for one/two tasks at a time
	- Each instruction is written in machine code that CPU operates on
- The more cores available, the more tasks can be ran in *parallel*


## High-Language Translation
?
- High level code can either be *compiled* into machine code by a *compiler* which is a separate software or CPU runs an *interpreter* program that loops over code and runs it
- Another approach is for compiler to create *bytecode* and VM running on CPU will run the bytecode
- Python VM (*PVM*) runs bytecode after *python3* is executed which compiles python code into a bytecode file
	- This is similar to JVM that runs class bytecode files after compilation, however *JVM*'s bytecode is closer to machine code


## GPUs
?
- GPUs: graphical processing units which contrary to CPU that has few cores that are fast and independent, has many *cores that are slow, float-optimized, and coordinated.*
.
- *FLOPS*: floating-point operations per second, way of measuring performance of GPUs
- *Benchmark*: program for measuring performance

## RAM
?
- Randomly accessed : fast at accessing different locations efficiently
- *Byte addressable*
	- Each byte of data has its own address that the CPU can use to access it
- *Fast, volatile, small*

## Storage
?
- *HDDS* (Hard Disk Drivers)
	- Bits stored on spinning magnetized platter
	- Moving head reads/writes data
- *SSDs* (Solid State Disks)
	- Bits stored in charged cells
	- No moving parts (faster)
- *Large, nonvolatile, slow*