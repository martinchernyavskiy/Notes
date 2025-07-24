### Repeatable Code
- Copying code over creates a lot of disadvantages
- Subroutines allow to reuse the same code, without a need of duplicating memory space allocation and creating any debugging hurdles

### Subroutine
- *Well-defined software modules that are written to perform a specific task*
- One copy of code, much more maintainable
- Previous address in sequence of tasks is stored in R7, called *return address*
- If call multiple subroutines, one in another, must save this address into memory and restore after
- Must specify which parameters are used, so the caller knows what registers are used. However, some registers might be used under the hood in the subroutine, a good rule of thumb is to save the data in these registers and restore upon completion of the subroutine
- Callers can pass parameters by either value or reference (memory location of parameter), depending on the logic of the subroutine. All still use registers
```
JSR test ; call subroutine


; Does this ....
; Assumes: R1 = character to use ; parameter 
; Returns: R1 = .... ; where stores the result, usually same register as parameter

test
	; store register data into the memory allocated by subroutine
	; code
	; code
	; code

; can branch to the exit logic 
label_exit
	; load saved register data back to the registers to restor before returning from subroutine
	RET

; allocate memory spaces for registers used below using BLKW
```
- ##### Advantages
	- Saves memory space
	- Encapsulates low-level information about the implementation
	- Maintainable code, easy to debug