# Bandit Level 12 to 12 Writeup

Author: [Akshay K Muraleedharan](https://github.com/Quantum_Glitch)


Problem Page: [Bandit12](https://overthewire.org/wargames/bandit/bandit13.html)
### List of Commands Used
* ssh  
Sets up SSH Connection to the OverTheWire Game Server.
* mkdir  
Makes a new directory.
* cp  
Copies files.
* cd  
Changes directory.
* xxd  
Used to encode/decode hexdumps.
* gzip  
Used for operations related to the gzip compression format.
* bzip2  
Used for operations related to the bzip2 compression format.
* tar  
Used for operations related to the tar archiving system.
* mv  
Used to move and rename files.
* cat
Used to concatenate files and output the result to stdout.
* file
Outputs the file properties of a given file.
* ls  
Lists out all the files and diectories under a certain directory.
### Walkthrough
The file data.txt is extremely compressed. Since we will be creating a lot of temporary files along the way, we make a new folder in /tmp directory. The first step is to get the actual compressed file from its hexdump, which is done by the xxd -d command. By default the output goes to stdout, so redirect it into a new file with any suitable filename.  
Now comes the _tedious_ decompression part. Using ls and file commands, find the file and its type. For the first step, we see that it is a gzip compressed file.  
> I initially tried to just use gzip -d, but it didnt work since we need a .gz file extension for gzip -d or gunzip to work. So use mv and add a filename with .gz at the end.

Repeat the process (with various other compression formats; use ls and file to keep track of the decompression progress, keep descriptive file names so that you dont get lost) until you get a text file. This contains the password.


#### Decompressing files in various formats:  
1. gzip  
Make sure the file has a .gz extension. Use gzip -d or gunzip.
2. bzip2  
Use bzip -d. Redirect the output to a new file.
3. tar  
Use tar -xf or -xvf if you want a more detailed description of what's happening. Use ls to find the extracted file.
### Password
* 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
### Bash script to automate the process
> #!/usr/bin/expect  
spawn ssh -p 2220 bandit12@bandit.labs.overthewire.org  
expect "password:"  
send -- "5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu\r"  
expect "$ "  
send -- "mkdir /tmp/temporaryb12\r"  
send -- "cp data.txt /tmp/temporaryb12\r"  
send -- "cd /tmp/temporaryb12\r"  
send -- "xxd -r data.txt>data1.gz\r"  
send -- "gzip -d data1.gz\r"  
send -- "bzip2 -d -c data1 > data2.gz\r"  
send -- "gzip -d data2.gz\r"  
send -- "tar -xf data2\r"  
send -- "tar -xf data5.bin\r"  
send -- "bzip2 -dc data6.bin>data6\r"  
send -- "tar -xf data6\r"  
send -- "mv data8.bin data8.bin.gz\r"  
send -- "gzip -d data8.bin.gz\r"  
send -- "cat data8.bin\r"  
send -- "exit\r"  
interact
