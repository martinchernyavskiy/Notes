### Assembly Language Programming
- Assembler produces object file containing binary program instructions from the program written in assembly language, loaded into the computer's memory
- Values in instructions can be expressed in decimal, hex, or binary
- Decimal (#)m, hex (x), binary (b)
- Negative numbers must be represented in decimal


### sum.asm
```asm
; comments explaining what the program does
; ...
; ...
; ...

	.ORIG x0200 ; tells the starting memory address

ADD R0, R1, R2
ADD R0, R0, R3
ADD R0, R0, R4

	. END ; indicates the end of the code
```
- *Assembler directives (.ORIG and .END* are not instructions, they are only used by the assembler
- .obj file contains location address specified by .ORIG directive on the first line
- The rest assembly instructions are converted in the appropriate 16 bit instructions that will be stored starting at the indicated address 

### Program Execution by Processor
- PC is forced to have .ORIG address 
- Processor follows instruction cycle, fetching, decoding and working through the instructions, always incrementing PC to the next memory address after decoding


### Essential Programming Skills
- Clearing Register (AND register with zero --> AND R1, R1, #0)
- Initializing to a specific value (immediate value of 5 bits): 
```
AND R3, R3, #0
ADD R3, R3, #7
```
- Copying value from one register to another:
```
ADD R1, R2, #0
; or
AND R1, R2, R2 ; since anding SR with itself yields same values
; or 
AND R1, R2, #-1 ; since -1 is all 1's in 2-s complement
```
- Subtraction isn't directly supported by LC-3 processor, however we simply apply addition of a number complement and the 2nd operand:
```
NOT R0, R4
ADD R0, R0, #1
ADD R0, R0, R3
```
- Masking 