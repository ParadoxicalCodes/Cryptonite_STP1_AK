# Challenge Description
So far, you have mostly been dealing with read permissions. This makes sense, because you have been making the /flag file readable to read it. In this level, we will explore execute permissions.

When you invoke a program, such as /challenge/run, Linux will only actually execute it if you have execute-access to the program file. Consider:
```bash
hacker@dojo:~$ ls -l /challenge/run
-rwxr-xr-x 1 root root    0 May 22 13:42 /challenge/run
hacker@dojo:~$ /challenge/run
Successfully ran the challenge!
hacker@dojo:~$
```
In this case, /challenge/run runs because it is executable by the hacker user. Because the file is owned by the root user and root group, this requires that the execute bit is set on the other permissions. If we remove these permissions, the execution will fail!
```bash
hacker@dojo:~$ chmod o-x /challenge/run
hacker@dojo:~$ ls -l /challenge/run
-rwxr-xr-- 1 root root    0 May 22 13:42 /challenge/run
hacker@dojo:~$ /challenge/run
bash: /challenge/run: Permission denied
hacker@dojo:~$
```
In this challenge, the /challenge/run program will give you the flag, but you must first make it executable! Remember your chmod, and get /challenge/run to tell you the flag!
# Thought Process & Solution

```bash
hacker@permissions~executable-files:~$ ls -l /challenge/run
-r--r-xr-x 1 hacker hacker 32 Jan 14  2025 /challenge/run
hacker@permissions~executable-files:~$ chmod u+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{kxc5-fFf6fywDYcN6Oszta71F2b.dJTM2QDL5EzN0czW}
```
**Flag:** `pwn.college{kxc5-fFf6fywDYcN6Oszta71F2b.dJTM2QDL5EzN0czW}`
## New Learning
## Reference
