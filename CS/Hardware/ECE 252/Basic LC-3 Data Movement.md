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


### Calculation of Memory Address
- Can't directly encode label's address into an instruction, won't fit the number of available bits (since memory address in LC-3 is 16 bit long)
- Encode how far away this address is from PC (*PC-Relative addressing mode*)
- LD: (opcode - DR - PCoffset9), aka. pc-relative memory read, where offset is added to *already-incremented PC value*
- *Effective address = $PC^+$ + PCOffset9*
- LD and ST can only access memory locations that are 9 2-s complement bits away from the current PC-value, thus 