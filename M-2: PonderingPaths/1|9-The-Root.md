# Challenge Description
Alright, so the filesystem starts at /. Under that, there are a whole mess of other directories, configuration files, programs, and, most importantly, flags. In this level, we've added a program right in /, called pwn, that will give you the flag. All you need to do for this level is to invoke this program!

You can invoke a program by providing its path on the command line. In this case, you'll be giving the exact path, starting from /, so the path would be /pwn. This style of path, one that starts with the root directory, is referred to as an "absolute path".

Start the challenge, launch a terminal, invoke the pwn program using its absolute path, and Capture that Flag! Good luck!
# Thought Process & Solution
I did ls first as a way to see whether i had to go inside another directory or not to, invoke my program but after re-reading the description - it clearly stated /pwn will give us the flag meaning my program is already in the root directory (as evident from output of cmd 'ls') i needed to call it.
```Bash
hacker@paths~the-root:~$ ls
COLLEGE  a.sh            flag          leap        planet      rm   the-flag
Desktop  cd              flaggg.txt    myflag      pwn         tee  x.sh
PWN      college_output  instructions  output.txt  pwn_output  the
hacker@paths~the-root:~$ /PWN
bash: /PWN: No such file or directory
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{E8YIaT9AbvhBwtIe8OIpUR50Xec.dhzN5QDL5EzN0czW}
```
**Flag:** `pwn.college{E8YIaT9AbvhBwtIe8OIpUR50Xec.dhzN5QDL5EzN0czW}`
## New Learning
<img width="703" height="344" alt="image" src="https://github.com/user-attachments/assets/ab88ab4d-913a-40b5-8806-dc2c47238363" />

Typical File system layout in linux, for windows its C: , D: etc

## Reference
Tagged video in the module - https://youtu.be/b67Jq6IZ3U8?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC
