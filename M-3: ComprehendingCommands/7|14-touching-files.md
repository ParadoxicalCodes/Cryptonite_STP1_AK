# Challenge Description

Of course, you can also create files! There are several ways to do this, but we'll look at a simple command here. You can create a new, blank file by touching it with the touch command:
```bash
hacker@dojo:~$ cd /tmp
hacker@dojo:/tmp$ ls
hacker@dojo:/tmp$ touch pwnfile
hacker@dojo:/tmp$ ls
pwnfile
hacker@dojo:/tmp$
```
It's that simple! In this level, please create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get your flag!
# Thought Process & Solution
First i went to /tmp to see what files are there, then i created the necessary files using touch as evident from the output of ls.
```bash
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ ls
bin  hsperfdata_root  tmp.TpSOPGOVKK
hacker@commands~touching-files:/tmp$ touch /tmp/pwn
hacker@commands~touching-files:/tmp$ ls
bin  hsperfdata_root  pwn  tmp.TpSOPGOVKK
hacker@commands~touching-files:/tmp$ touch /tmp/college
hacker@commands~touching-files:/tmp$ cd
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{w48N67spTwn9JhG64Kd2NdmE_aR.dBzM4QDL5EzN0czW}
```
**Flag:** `pwn.college{w48N67spTwn9JhG64Kd2NdmE_aR.dBzM4QDL5EzN0czW}`
## New Learning
touch cmd - create new files in a directory (Ctrl N of linux basically)
## Reference
