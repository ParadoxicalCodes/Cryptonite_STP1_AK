# Challenge Description
In the last level, you did cat flag to read the flag out of your home directory! You can, of course, specify cat's arguments as absolute paths:
```bash
hacker@dojo:~$ cat /challenge/DESCRIPTION.md
In the last level, you did `cat flag` to read the flag out of your home directory!
You can, of course, specify `cat`'s arguments as absolute paths:
...
```
In this directory, I will not copy it to your home directory, but I will make it readable. You can read it with cat at its absolute path: /flag.
> FUN FACT: /flag is where the flag always lives in pwn.college, but unlike in this challenge, you typically can't access that file directly.
# Thought Process & Solution
I did ls first to see if my flag is there but its not there as mentioned in the challenge description but as i was told the flag is there in /flag, so cat /flag give us our flag.
```bash
hacker@commands~catting-absolute-paths:~$ ls
COLLEGE  a.sh            flaggg.txt    myflag      pwn         t    the-flag
Desktop  cd              instructions  output.txt  pwn_output  tee  x.sh
PWN      college_output  leap          planet      rm          the
hacker@commands~catting-absolute-paths:~$ cat /challenge/flag
cat: /challenge/flag: No such file or directory
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{IqJYiHWDagUdUXxW9j-Kmcl3MT9.dlTM5QDL5EzN0czW}
```
**Flag:** `pwn.college{IqJYiHWDagUdUXxW9j-Kmcl3MT9.dlTM5QDL5EzN0czW}`
## New Learning
## Reference
