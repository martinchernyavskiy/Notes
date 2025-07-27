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

	; context restore
	LD R1, getchar_R1
	LD R2, getchar_R2
	RET

getchar_R1 .BLKW 1
getchar_R2 .BLKW 1

IO_BASE .FILL xFE00 ; start of memory mapped I/O
```