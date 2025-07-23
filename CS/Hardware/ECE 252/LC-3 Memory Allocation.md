### Terminology
- Data allocation directives allow for setting up memory space for variables to use in the program.
- Labels are used as symbolic addresses, the assembler chooses the actual addresses
- *Allocate*: reserve space in memory
	- No code or variable will be placed there
- *Initialize*: set value in memory location when program is loaded
	- Happens before program executes


### Memory Allocation Directives
*Label is optional symbolic address of the first word of memory allocated*

- #### \<Label>   .FILL value
	- Allocates one location and initializes it to value
```
; allocate one word initialized to -1 (xFFFF)
NEG1   .FILL #-1

; allocate and initialize two words where
; the label ARRAY is address of first word
ARRAY   .FILL #42
		.FILL x17
```
- #### \<Label>   .BLKW count
	- Allocates count words of memory, not initialized
	- They may be of values other than 0
	- Used for storing results than variables
```
; allocates one unitialized memory word at the
; memory address corresponding to the ONEWORD label
ONEWORD   .BLKW #1

; allocates 42 uninitialized memory words,
; where the first word is at the BIGBLOCK label
BIGBLOCK  .BLKW #42
```
	
- #### \<Label>   .STRINGZ "string"
	- Allocates and initializes memory to hold ASCIIZ string (null terminates sequence of ASCII characters)
```

```