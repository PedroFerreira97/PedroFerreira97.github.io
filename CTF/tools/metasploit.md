# MetaSploit Components:

	**msfconsole**	
the main command-line interface.

	**Modules**	
supporting modules such as exploits, scanners, payloads, etc.

	**Tools**		
Stand-alone tools that will help vulnerability research, vulnerability assessment, or penetration testing. Some of these tools are msfvenom, pattern_create and pattern_offset. We will cover msfvenom within this module, but pattern_create and pattern_offset are tools useful in exploit development which is beyond the scope of this module. 


### Find Modules

	cd /otp/metasploit-framework-5101/modules
	tree -L 1 auxiliary
	tree -L 1 encoders
	tree -L 1 evasion
	tree -L 1 exploits
	tree -L 1 nops
	tree -L 1 payloads
	tree -L 1 post

### msfconsole
	help set
	history
        back
        search xx17.10

	1) use exploit/..../...
	2) ls
	3) show options
	4) show payloads
	5) info
	6) set requirements 
	7) set rhosts 10.10.165.39	
	8) exploit -z OR run
	9) check (Some modules support the check option. This will check if the target system is vulnerable without exploiting it.)
	10) background
	11) sessions
	12) sessions -i X


When in session
- shell
- hashdump
- dir (ls)
- cd
- search -f FILE.TXT
- cat

