### LC-3 Keyboard Input
- Consists of two registers, mapped into the LC-3 memory space
	- Keyboard Status Register (KBSR), mapped to 0xFE00
		- KBSR[15] == 1 means that a new character is available, 0 otherwise
	- Keyboard Data Register (KBDR), mapped to 0xFE02
		- KBDR[7:0] contains ASCII code of the last typed character
		- Reading from KBDR automatically resets 15th bit of the KBSR
- Repeatedly check KBSR until it indicates that a key has been pressed (*BRn*)
- When character is available, read it from KBDR

### getchar
```asm
; getchar
; Gets (waits for) a character from keyboard
; Assumes: Nothing
; Returns: R0 = character

getchar
	; context save
	ST R1, getchar_R1
	ST R2. getchar_R2
	
	LD R1, IO_BASE ; get I/O base address
getchar_wait
	LDR R2, R1,#0 ; read KBSR
	BRzp getchar_wait ; wait until keyboard has data
	LDR R0, R1, #2 ; read char from KBDR
getchar_exit
	; context restore
	LD R1, getchar_R1
	LD R2, getchar_R2
	RET

getchar_R1 .BLKW 1
getchar_R2 .BLKW 1

IO_BASE .FILL xFE00 ; start of memory mapped I/O
```

### LC-3 Character Display Output
- Consists of two registers:
	- Display Status Register (DSR), mapped to 0xFE04
		- DSR[15] is 1 if display is ready, 0 otherwise
	- Display Dat Register (DDR), mapped to 0xFE06
		- Character written to it is displayed on screen
- Poll the DSR until it's ready, then write character to DDR

```asm
; sendchar
; Displays character to display
; Assumes: R0 contains the character to display
; Returns : Nothing

sendchar
	; context save
	ST R1, sendchar_R1
	ST R2, sendchar_R2
	
	LD R1, IO_BASE ; get I/O base address
sendchar_wait
	LDR R2, R1, #4 ; read DSR
	BRzp sendchar_wait ; wait until display is ready
	STR R0, R1, #6 ; write character to DDR
sendchar_exit
	; context restore
	LD sendchar_R1
	LD sendchar_R2
	RET

sendchar_R1 .BLKW 1
sendchar_R2 .BLKW 1
IO_BASE .FILL xFE00 ; start of memory mapped I/o

```