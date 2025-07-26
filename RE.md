# REVERSE ENGNEERING

- gdb (GNU Debugger)
	-- # gcc -o executable main.c -g  (to include debugging symbols)
	-- (gdb) break main ( to set break point at main )
	-- (gdb) run (to run the programme)
	-- (gdb) next (to run next instruction of C)
	-- (gdb) nexti (to execute next instruction of assambly)

	analys variables
	-- (gdb) info variables (to see all variables )
	-- (gdb) info variables ^name$  (to see varible with name 'name')
	-- (gdb) x/s 0x5555556010  (to see string array from an address)
	-- (gdb) x/d 0x5555556010   (to see a decimal value at this address)
	-- (gdb) x/22d 0x5555556010   (to see a decimal values of next 22 addresses from this address)