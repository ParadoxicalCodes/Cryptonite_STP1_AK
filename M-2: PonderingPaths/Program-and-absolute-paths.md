# Challenge Description
Let's explore a slightly more complicated path! Except for in the previous level, challenges in pwn.college are in the challenge directory and the challenge directory is, in turn, right in the root directory (/). The path to the challenge directory is, thus, /challenge. The name of the challenge program in this level is run, and it lives in the /challenge directory. Thus, the path to the run challenge program is /challenge/run.

This challenge again requires you to execute it by invoking its absolute path. You'll want to execute the run file that is in the challenge directory that is, in turn, in the / directory. If you invoke the challenge correctly, it will give you the flag. Good luck!
# Thought Process & Solution
Executed "ls" to see for all directories, and i notice "flag", so i outputted its content which seems to be my flag?
After this i ran the actual cmd written in description which gave our flag but the two flags i got dont match. Surprisingly both are correct, I am guessing each time i call the command /challenge/run new flag is generated and stored in "flag" file possibly? or idk.
```Bash
hacker@paths~program-and-absolute-paths:~$ ls
COLLEGE  a.sh            flag          leap        planet      rm   the-flag
Desktop  cd              flaggg.txt    myflag      pwn         tee  x.sh
PWN      college_output  instructions  output.txt  pwn_output  the
hacker@paths~program-and-absolute-paths:~$ cat flag
pwn.college{407nfghFqa9Zs3cALiHHWd2_f5r.dFzN1QDL5EzN0czW}
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{sUG-AbfVZKErHQxKjgVrCo58vPf.dVDN1QDL5EzN0czW}
```
**Flag:** `pwn.college{sUG-AbfVZKErHQxKjgVrCo58vPf.dVDN1QDL5EzN0czW}`
## New Learning
Nothing much apart from calling a program thats in directory challenge which is inside the root directory.
## Reference
