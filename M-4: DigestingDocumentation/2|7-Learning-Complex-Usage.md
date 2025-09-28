# Challenge Description
While using most commands is straightforward, the usage of some commands can get quite complex. For example, the arguments to commands like sed and awk, which we're definitely not getting into right now, are entire programs in an esoteric programming language! Somewhere on the spectrum between cd and awk are commands that take arguments to their arguments...

This sounds crazy, but you've already encountered this with the find level in Basic Commands. find has a -name argument, and the -name argument itself takes an argument specifying the name to search for. Many other commands are analogous.

Here is this level's documentation for /challenge/challenge:

> Welcome to the documentation for /challenge/challenge! This program allows you to print arbitrary files to the terminal, when given the --printfile argument. The argument to the --printfile argument is the path of the flag to read. For example, /challenge/challenge --printfile /challenge/DESCRIPTION.md will print out the description of the level!

Given that documentation, go get the flag!
# Thought Process & Solution
I first ran the command with no arguments just to see if there are any other hints i missed -  no hints. Next i used --printfile argument to print description.md as told in description - for any hints. Then here i got confused what argument would yield me the flag decided to just print /challenge/challenge which gives me a script but i couldnt glean any useful hints. So next i decided to print /challenge/flag but no file exists which led me to reaLise our flag is saved as /flag why would it be in /challenge/flag.
```bash
hacker@man~learning-complex-usage:~$ ls /challenge/challenge
/challenge/challenge
hacker@man~learning-complex-usage:~$ /challenge/challenge
Incorrect usage! You must pass an argument to me (read the challenge 
description for details).
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /challenge/DESCRIPTION.md
Correct argument! Here is the /challenge/DESCRIPTION.md file:
While using most commands is straightforward, the usage of some commands can get quite complex.
For example, the arguments to commands like `sed` and `awk`, which we're definitely not getting into right now, are entire programs in an esoteric programming language!
Somewhere on the spectrum between `cd` and `awk` are commands that take arguments to their arguments...
 
This sounds crazy, but you've already encountered this with the `find` level in [Basic Commands](/linux-luminarium/commands).
`find` has a `-name` argument, and the `-name` argument itself takes an argument specifying the name to search for.
Many other commands are analogous.
 
Here is this level's documentation for `/challenge/challenge`:
 
> Welcome to the documentation for `/challenge/challenge`! This program allows you to print arbitrary files to the terminal, when given the `--printfile` argument. The argument to the `--printfile` argument is the path of the flag to read. For example, `/challenge/challenge --printfile /challenge/DESCRIPTION.md` will print out the description of the level!
 
Given that documentation, go get the flag!
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /challenge/challenge
Correct argument! Here is the /challenge/challenge file:
#!/opt/pwn.college/bash
 
if [ "$#" -eq 0 ]
then
	fold -s <<< "Incorrect usage! You must pass an argument to me (read the challenge description for details)."
	exit 1
fi
 
if [ "$1" != "--printfile" ]
then
	fold -s <<< "Incorrect usage! You passed the wrong argument (read the challenge description for details)."
	exit 2
fi
 
if [ "$#" -eq 1 ]
then
	fold -s <<< "You must pass a file for --printfile to read!"
	exit 3
fi
 
echo "Correct argument! Here is the $2 file:"
cat "$2"
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /challenge/flag
Correct argument! Here is the /challenge/flag file:
cat: /challenge/flag: No such file or directory
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile
You must pass a file for --printfile to read!
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{0KUvPQebMO5VDGqN6-lhnS4wcsO.dVjM5QDL5EzN0czW}
hacker@man~learning-complex-usage:~$ ls
COLLEGE  a.sh            flaggg.txt    myflag        planet      rm   the
Desktop  cd              instructions  not-the-flag  pwn         t    the-flag
PWN      college_output  leap          output.txt    pwn_output  tee  x.sh
hacker@man~learning-complex-usage:~$ ls /
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
```
**Flag:** `pwn.college{0KUvPQebMO5VDGqN6-lhnS4wcsO.dVjM5QDL5EzN0czW}`
## New Learning
## Reference
