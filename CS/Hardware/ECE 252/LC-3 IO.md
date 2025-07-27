### LC-3 Keyboard Input
- Consists of two registers, mapped into the LC-3 memory space
	- Keyboard Status Register (KBSR), mapped to 0xFE00
		- KBSR[15] == 1 means that a new character is available, 0 otherwise
	- Keyboard Data Register (KBDR), mapped to 0xFE02
		- KBDR[7:0] contains ASCII code of the last typed character
		- Reading from KBDR automatically resets 15th bit of the KBSR