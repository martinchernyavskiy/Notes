### Universal Computational Device (computer)
- Description of the task (program)
- Input data 

### Arithmetic Logic Unit (ALU)
- Computational multi-functional structure in a processor that performs arithmetic or logical operations
- The logic operations are bitwise in ALU 
- All logic structures work in parallel, however for one step of a program only one result of those operations is needed
- *Use multiplexers to select the result*, which are controlled by a select signal mode to choose which logic structure output to select.


### Register File
- Small memory located near the ALU
- Contains multiple registers which can be written to / read from
- Allows for reading from multiple locations simultaneously by having multiple read ports, but write to only one location 
- ![[Pasted image 20250709075603.png]]

### Processing Unit
- Contains ALU and the register file and does main computational work of a processor

### Control Unit
- Analyzes instructions and orchestrates other computer resources to execute the instruction
- Instructions are held in memory

### Stored program computer
- Allows for executing different programs by writing different program into memory (which stores its set of instructions to be executed).
- Assume computer executes one instruction at a time