# Challenge Description
Files are all around you. Like candy wrappers, there'll eventually be too many of them. In this level, we'll learn to clean up!

In Linux, you remove files with the rm command, as so:
```bash
hacker@dojo:~$ touch PWN
hacker@dojo:~$ touch COLLEGE
hacker@dojo:~$ ls
COLLEGE     PWN
hacker@dojo:~$ rm PWN
hacker@dojo:~$ ls
COLLEGE
hacker@dojo:~$
```
Let's practice. This challenge will create a delete_me file in your home directory! Delete it, then run /challenge/check, which will make sure you've deleted it and then give you the flag!
# Thought Process & Solution
Did ls to see if my target file is in home dir as told then deleted it after verifying it and running /challenge/check gave the flag.
```bash
hacker@commands~removing-files:~$ ls
COLLEGE  a.sh            delete_me     leap        planet      rm   the
Desktop  cd              flaggg.txt    myflag      pwn         t    the-flag
PWN      college_output  instructions  output.txt  pwn_output  tee  x.sh
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ ls
COLLEGE  a.sh            flaggg.txt    myflag      pwn         t    the-flag
Desktop  cd              instructions  output.txt  pwn_output  tee  x.sh
PWN      college_output  leap          planet      rm          the
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{EZ-lApC3CvTDva7cICuSJjYy9TN.dZTOwUDL5EzN0czW}
```
**Flag:** `pwn.college{EZ-lApC3CvTDva7cICuSJjYy9TN.dZTOwUDL5EzN0czW}`
## New Learning
rm - deletes file, arguments it can take as file name or file path
## Reference
