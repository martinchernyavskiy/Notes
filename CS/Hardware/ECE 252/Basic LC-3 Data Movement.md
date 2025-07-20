### Memory Access
- Since REG File contains only 8 registers, some programs may need to read/write from memory since there are $2^{16}$ registers
- REG File is too small to be used for storage space, it can be viewed rather as a temporary storage for data to be used in ALU operations


### Label as a Location
- Similar to variables in programming
- Assembler directive is used for naming a memory location that will hold a word of data instead of instruction
- Data movement instructions access labeled memory locations and when the assembler assembles the program, labels are converted into information used to calculate memory address
#### Example
```
NUM     .FILL x42 ; reserve 1 memory location, call NUM, initialize to                     ; hex 42
```
#### Load
```
LD  R0, NUM ; uses label as memory address to load from
```
#### Store
```
ST  R6, NUM ; uses label as a memory address to store to
```