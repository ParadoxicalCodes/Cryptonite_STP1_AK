# Challenge Description
The Linux filesystem has tons of directories with tons of files. You can navigate around directories by using the cd (change directory) command and passing a path to it as an argument, as so:
```Bash
hacker@dojo:~$ cd /some/new/directory
hacker@dojo:/some/new/directory$
```

This affects the "current working directory" of your process (in this case, the bash shell). Each process has a directory in which it's currently hanging out. The reasons for this will become clear later in the module.

As an aside, now you can see what the ~ was in the prompt! It shows the current path that your shell is located at.

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program. Good luck!
# Thought Process & Solution
## Attempt1
Same process as before, ls to see the root dir contents. I see instructions and cat it to see if any hints are there but i end up confused so just cat the flag for answer.
```Bash
hacker@paths~position-thy-self:~$ ls
COLLEGE  a.sh            flag          leap        planet      rm   the-flag
Desktop  cd              flaggg.txt    myflag      pwn         tee  x.sh
PWN      college_output  instructions  output.txt  pwn_output  the
hacker@paths~position-thy-self:~$ cat instructions
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
hacker@paths~position-thy-self:~$ /myflag/challenge/run
bash: /myflag/challenge/run: No such file or directory
hacker@paths~position-thy-self:~$ cd /myflag
bash: cd: /myflag: No such file or directory
hacker@paths~position-thy-self:~$ cat flag
pwn.college{407nfghFqa9Zs3cALiHHWd2_f5r.dFzN1QDL5EzN0czW}
```
**Flag:** `pwn.college{407nfghFqa9Zs3cALiHHWd2_f5r.dFzN1QDL5EzN0czW}`

## Attempt2
I tried solving this as it was intended and i recall there was a statement in instructions telling it will check and give me the hint for correct dir to move to, so i go for /challenge/run anyway to get the hint and this time i see how to do it. ~~But what i dont understand here is why i couldnt do cd /var/log/challenge/run ?~~
i see why - /challenge/run is the program, cd would shift me to the dir smh i jumbled up the commands a bit.
```Bash
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /var/log directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /var/log/challenge/run
bash: cd: /var/log/challenge/run: No such file or directory
hacker@paths~position-thy-self:~$ cd /var/log
hacker@paths~position-thy-self:/var/log$ ls
alternatives.log  bootstrap.log  faillog         lastlog   private
apache2           btmp           fontconfig.log  mysql     sysstat
apt               dpkg.log       journal         pcapdump  wtmp
hacker@paths~position-thy-self:/var/log$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{Iq05jH8Ww0h-v0N030uF5jv_NUE.dZDN1QDL5EzN0czW}
```
**Flag:** `pwn.college{407nfghFqa9Zs3cALiHHWd2_f5r.dFzN1QDL5EzN0czW}`
