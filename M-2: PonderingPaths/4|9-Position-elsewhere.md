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
Same process as before and both flags work.
```Bash
hacker@paths~position-elsewhere:~$ ls
COLLEGE  a.sh            flag          leap        planet      rm   the-flag
Desktop  cd              flaggg.txt    myflag      pwn         tee  x.sh
PWN      college_output  instructions  output.txt  pwn_output  the
hacker@paths~position-elsewhere:~$ cat instructions
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag
 
[HYPE] ONWARDS TO GREATNESS!
 
[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.
 
[TEST] You should have redirected my stdout to a file called myflag. Checking...
 
[PASS] The file at the other end of my stdout looks okay!
 
[TEST] You should have redirected my stderr to instructions. Checking...
 
[PASS] The file at the other end of my stderr looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@paths~position-elsewhere:~$ cat output.txt
Usage: /challenge/pwn --secret [SECRET_ARG]
 
SECRET_ARG should be "gevp4ac-"
hacker@paths~position-elsewhere:~$ cat flag
pwn.college{407nfghFqa9Zs3cALiHHWd2_f5r.dFzN1QDL5EzN0czW}
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/aarch64-linux-gnu/include/gnu directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /usr/aarch64-linux-gnu/include/gnu
hacker@paths~position-elsewhere:/usr/aarch64-linux-gnu/include/gnu$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{8X6NDaXvd8dhQFyR5ZqAKsQuswt.ddDN1QDL5EzN0czW}
```
**Flag:** `pwn.college{8X6NDaXvd8dhQFyR5ZqAKsQuswt.ddDN1QDL5EzN0czW}`
