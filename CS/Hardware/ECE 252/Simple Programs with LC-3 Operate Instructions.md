### Assembly Language Programming
- Assembler produces object file containing binary program instructions from the program written in assembly language, loaded into the computer's memory


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