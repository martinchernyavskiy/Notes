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
- Fetches instructions, one at a time, from memory and communicated with other parts of computer on how to execute each instruction (like choosing control signals in ALU)

- Contains 2 special registers
	- Program Counter (PC): address of next instruction (pointer)
	- Instruction Register (IR): holds current instruction, decoded by control unit

- Control unit executes an instruction when PC contains its address.
	- Reads from the memory address
	- Updates instruction register with its contents (process called fetching)
	- Increments Program Counter
	- Decodes the instruction in IR

### Stored program computer
- Allows for executing different programs by writing different program into memory (which stores its set of instructions to be executed).
- Assume computer executes one instruction at a time