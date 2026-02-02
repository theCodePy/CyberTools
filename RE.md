# REVERSE ENGNEERING

- gdb (GNU Debugger)
	-- # gcc -o executable main.c -g  (to include debugging symbols)

	view addresses mapping
	-- (gdb) info proc mappings  (view address mapping after running the program)

	Set breakpoints
	-- (gdb) break main ( to set break point at main )
	-- (gdb) break *0x5555555552f6   (set the breakpoint using the hexadecimal format)
	-- (gdb) break *(0x555555554000 + 0x12f6)   (set breakpoint using (base address + offset))
	
	run the program inside gdb
	-- (gdb) start    ( it will pause at the main function (or entry point))
	-- (gdb) starti    ( to stop at the very first instruction )
	-- (gdb) run (to run the programme)
	-- (gdb) next (to run next instruction of C)
	-- (gdb) nexti (to execute next instruction of assambly)

	analys variables
	-- (gdb) info variables (to see all variables )
	-- (gdb) info variables ^name$  (to see varible with name 'name')
	-- (gdb) x/s 0x5555556010  (to see string array from an address)
	-- (gdb) x/d 0x5555556010   (to see a decimal value at this address)
	-- (gdb) x/22d 0x5555556010   (to see a decimal values of next 22 addresses from this address)

	Pass arguments
	You can simply provide the arguments directly after the run or start command.
	-- (gdb) run "CTFlearn{test_flag}"   
	-- (gdb) start "CTFlearn{test_flag}"
	-- (gdb) set args "CTFlearn{test_flag}"   ( Set arguments persistently )
	-- $ gdb --args ./program "CTFlearn{test_flag}"  ( set arguments From the command line )
	-- (gdb) show args  ( verify what you passed )