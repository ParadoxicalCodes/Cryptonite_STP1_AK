# Challenge Description
The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:
```bash
hacker@dojo:~$ cd /some/new/directory
hacker@dojo:/some/new/directory$
```
This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.

As an aside, now you can see what the ~ was in the prompt! It shows the current path that your shell is located at.

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. Good luck!
# Thought Process & Solution
Nothing much to add here.
```bash
hacker@paths~position-yet-elsewhere:~$ ls
COLLEGE  a.sh            flag          leap        planet      rm   the-flag
Desktop  cd              flaggg.txt    myflag      pwn         tee  x.sh
PWN      college_output  instructions  output.txt  pwn_output  the
hacker@paths~position-yet-elsewhere:~$ cat flag
pwn.college{407nfghFqa9Zs3cALiHHWd2_f5r.dFzN1QDL5EzN0czW}
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /proc/143 directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /proc/143
hacker@paths~position-yet-elsewhere:/proc/143$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{4eRS1i6sSYcYhVYmKtoPsl3keCT.dhDN1QDL5EzN0czW}
```
**Flag:** `pwn.college{4eRS1i6sSYcYhVYmKtoPsl3keCT.dhDN1QDL5EzN0czW}`
## New Learning
## Reference
