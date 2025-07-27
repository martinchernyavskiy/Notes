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


	LD R1, IO_BASE


	RET

IO_BASE .FILL xFE00 ; start of memory mapped I/O
```