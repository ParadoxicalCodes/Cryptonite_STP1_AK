# Challenge Description
Next, let's learn about ?. When it encounters a ? character in any argument, the shell will treat it as a single-character wildcard. This works like *, but only matches one character. For example:
```bash
hacker@dojo:~$ touch file_a
hacker@dojo:~$ touch file_b
hacker@dojo:~$ touch file_cc
hacker@dojo:~$ ls
file_a	file_b	file_cc
hacker@dojo:~$ echo Look: file_?
Look: file_a file_b
hacker@dojo:~$ echo Look: file_??
Look: file_cc
```
Now, practice this yourself! Starting from your home directory, change your directory to /challenge, but use the ? character instead of c and l in the argument to cd! Once you're there, run /challenge/run for the flag!
# Thought Process & Solution
As told in desc i replaced c and l with ? and shifted to my target dir then ran my program which gave us our flag.
```bash
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ ./run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{Mv6wu9hazfVmg_qfT4Pg-hm5NEi.dJjM4QDL5EzN0czW}
```
**Flag:** `pwn.college{Mv6wu9hazfVmg_qfT4Pg-hm5NEi.dJjM4QDL5EzN0czW}`
## New Learning
## Reference
