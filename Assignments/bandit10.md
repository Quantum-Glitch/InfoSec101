# Bandit Level 10 to 11 Writeup

Author: [Akshay K Muraleedharan][GITHUBPROFILE]


Problem Page: [Bandit10][BANDITPAGE]
### List of Commands Used
* ssh  
Sets up SSH Connection to the OverTheWire Game Server.
* base64
Used for encoding/decoding data in base64 format.
### Walkthrough
The page tells us that the data is encoded in base64 format. Looking at the man page for the base64 command, we can find that the -d option decodes the base64 data from a text file and outputs it to stdout. This gives us the password for the next level.
### Password
* IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
###Bash script to automate the process
> #!/usr/bin/expect
spawn ssh -p 2220 bandit10@bandit.labs.overthewire.org
expect "password:"
send -- "truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk\r"
expect "$ "
send -- "base64 -d data.txt \r"
send -- "exit\r"
interact
