# RustScan

## Installing RustScan

- Go to RustScan Repo (https://github.com/RustScan/RustScan/wiki/Installation-Guide)
- Download the .deb file for Kali Linux.(rustscan_1.8.0_amd64.deb)
- dpkg -i <file name>  
- Try running rustscan in terminal.

## Accessible

RustScan is actively accessible. That means we:

- Use continuous integration testing to ensure accessibility needs are met
- Manually test accessibility

## Fast

RustScan is fast. But, why? In short:

- Low-level kernel networking
- Written in a fast language (Rust)
- Asynchronous scanning. Multi-threading is slow due to the context switching cost. Async is fast. See my Rust room for more information on this.

## Extensible

1. RSE supports these languages:
-    Python
-    Shell
-    Perl
-    Any program which is a binary and in $PATH

2. Scripting Engine Arguments
 
RustScan's scripting engine can be altered using the "--scripts" argument.
There are 3 possible arguments:
-    None (don't run any scripts)
-    Custom (run all scripts in the scripts folder)
-    Default (runs Nmap script, or whatever script is in the config file. Default does not need to be enabled, it is on by default.)

3. Python Custom Scripts
4. Tags
5. Developer
6. Trigger Point
7. Call Format
8. The code itself
9. Contributing/Making Scripts
10. Running other tools with Rustscan

What is the scripting file config called?

- rustscan_scripts.toml

Can you run other binaries with RustScan? (T)rue / (F)alse.

- True

Does RutScan support scripts in Javascript? (T)rue / (F)alse.

- False

## Adaptive

RustScan is adaptive. That means it changes how it works to better suit its environment. We call this the "adaptive learning" feature set.

## Scanning

Basic Format
- rustscan -r ports -a  <Target-ip> -- <nmap cmds> 	(basic format)
- rustscan -a 127.0.0.1,0.0.0.0				(Multiple IP Scanning)
- rustscan -a www.google.com, 127.0.0.1			(Host Scanning)
- rustscan -a 192.168.0.0/30				(CIDR support)
- rustscan -a 'hosts.txt'				(Hosts file as input)
- rustscan -a 127.0.0.1 -p 53				(Individual Port Scanning)
- rustscan -a 127.0.0.1 -p 53,80,121,65535		(Multiple selected port scanning)
- rustscan -a 127.0.0.1 --range 1-1000			(Ranges of ports)
- rustscan -a 127.0.0.1 -- -A -sC			(Adjusting the Nmap arguments)
- rustscan -a 127.0.0.1 --range 1-1000 --scan-order "Random"	(Random Port Ordering)

1. rustscan -a MachineIp --range 1-1000
2. rustscan -a MachineIp -p 22 -- -sV
3. rustscan -a MachineIp -p 22,80 -- -sC

## RustScan QUiz

    First, how do you access the help menu?

-    Answer: -h

    Often referred to as “quiet” mode, What switch can do this?

-    Answer: -q

    Which switch can help us to scan for a particular Range?

-    Answer: -r

    What switch would you use to find out RustScan’s version?

-    Answer: -v
    
    Which switch will help us to select batch size?

-    Answer: -b

    Which switch can set timeout?

-    Answer: -t



