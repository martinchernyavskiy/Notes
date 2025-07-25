### Program Design and Coding
- #### Top-down Design
- Start design at top level and work way down to the subroutine hierarchy
- Develop flowcharts for each subroutine
- #### Bottom-up Coding
- Code up subroutines first to test and ensure they work properly before moving up a level

### strupr design
Start

get char

is null? (T/F)

If not null, convert to uppercase using toupper

save char

increment string pointer

iterate to is null until reach the end of the string

End (string is null)

### STRUPR
- R1 contains the address of ASCIIZ string
- *Uses pass-by-reference*
- Does not return a result
```asm

```

### TOUPPER
- sub-subroutine, used to assist strupr subroutine
- processes a single lowercase character, making it uppercase and skipping it if it wasn't lowercase to begin with
- R1: address of ASCIIZ string
- Use R0 as a way to store the each character
```
; NAME : TOUPPER
; DESCRIPTION : Converts lowercase letters in a string to uppercase
; ASSUMES: R0 contains character to convert 
; RETUNRS: R0 with 0 if character wasn't converted, uppercased 

JSR ISLOWER
BRz ; the character is not lower, increment pointer

```

### ISLOWER
- a sub-sub-subroutine that asissts toupper with determining whether a character is lovercase or not
- Use character from R0 to compute whether it's lower or not
```
; NAME: ISLOWER
; DESCRIPTION: Checks if character is lowercase or not
; ASSUMES: R0 contains character to check
; RETURNS: R0 with 0 if character is not lowercase, returns character otherwise

ISLOWER
	ST R7, ISLOWER_R7
	ST R2, ISLOWER_R2
	ST R3, ISLOWER_R3
	ST R4, ISLOWER_R4

	; load lowercase letter range endpoints to check if specified character is in the range or not
	LD R3, START_RANGE ; load hex code of 'a' as lowest point of range
	LD R4, END_RANGE ; load hex code of 'z' as highest point of range

	; negate the endpoints to use as a substraction operands
	NOT R3, R3
	ADD R3, R3, #1
	NOT R4, R4
	ADD R4, R4, #1


ISLOWER_CHECK
	ADD R2, R0, #0 ; copy character to use for checking if it's in the range of lowercase letters
	
	; check if character is less than the range of lowercase letters
	ADD R2, R2, R3 ; subtracts hex of 'a' from character
	BRn IS_LOWER_FALSE ; if previous computation resulted in negative, then character lies below range -> not lowercase

	; check if character is greater than the range of lowercase letters
	ADD R2, R0, #0 ; restore character hex value to second register
	ADD R2, R2, R4 ; subtracts hex of 'z' from character
	BRp IS_LOWER_FALSE ; if previous computation resulted in positive, then cahracter lies above the range -> not lowercase

	BR IS_LOWER_EXIT ; character is lowercase, exit subroutine

ISLOWER_FALSE
	AND R0, R0, #0 ; clears the character register, indicating that the character is not lowercase

ISLOWER_EXIT
	; context restore the registers in use
	LD R7, ISLOWER_R7
	LD R2, ISLOWER_R2
	LD R3, ISLOWER_R3
	LD R4, ISLOWER_R4
RET

; subroutine data
ISLOWER_R7 .BLKW 1 ; space to store R7 address for proper return logic
ISLOWER_R2 .BLKW 1 ; space to store data from initial R2 for context restoration
ISLOWER_R3 .BLKW 1 ; space to store data from initial R3 for context restoration
ISLOWER_R4 .BLKW 1 ; space to store data from initial R4 for context restoration
START_RANGE .FILL x61 ; hex value of a which is the first lowercase letter
END_RANGE .FILL x7A ; hex value of z which is the last lowercase letter
```
1111 1111 1111 1011

