# Challenge Description
You can also move files around with the mv command. The usage is simple:
```bash
hacker@dojo:~$ ls
my-file
hacker@dojo:~$ cat my-file
PWN!
hacker@dojo:~$ mv my-file your-file
hacker@dojo:~$ ls
your-file
hacker@dojo:~$ cat your-file
PWN!
hacker@dojo:~$
```
This challenge wants you to move the /flag file into /tmp/hack-the-planet (do it)! When you're done, run /challenge/check, which will check things out and give the flag to you.
# Thought Process & Solution
My doubt is cleared here i got confused as to where my flag file was and i was trying to look for it in /home/hacker dir but my file is stored in root dir i.e. "/" which i verified below with ls.
Back to question, i assumed mv takes both filenames and filepaths as arguments, so i filled in the absolute path for both source and destination - which led to solving the challenge.
```bash
hacker@commands~moving-files:~$ ls
COLLEGE  a.sh            flaggg.txt    myflag      pwn         t    the-flag
Desktop  cd              instructions  output.txt  pwn_output  tee  x.sh
PWN      college_output  leap          planet      rm          the
hacker@commands~moving-files:~$ cd /
hacker@commands~moving-files:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@commands~moving-files:/$ cd
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{0HxoOJdw3TSuER5N52koe6I64Qg.QX5ETM3EDL5EzN0czW}
```
**Flag:** `pwn.college{0HxoOJdw3TSuER5N52koe6I64Qg.QX5ETM3EDL5EzN0czW}`
## New Learning
mv cmd - moves files from one place to another
       - can have filename or its path as argument too
## Reference
