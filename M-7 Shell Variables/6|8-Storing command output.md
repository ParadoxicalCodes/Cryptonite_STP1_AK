# Challenge Description
In the course of working with the shell, you will often want to store the output of some command into a variable. Luckily, the shell makes this quite easy using something called Command Substitution! Observe:
```bash
hacker@dojo:~$ FLAG=$(cat /flag)
hacker@dojo:~$ echo "$FLAG"
pwn.college{blahblahblah}
hacker@dojo:~$
```
Neat! Now, you practice. Read the output of the /challenge/run command directly into a variable called PWN, and it will contain the flag!
# Thought Process & Solution
I forgot here for a moment how to read the variable.
```bash
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ cat PWN
COLLEGE
hacker@variables~storing-command-output:~$ cat $PWN
cat: pwn.college{oFEArUG07-LaHK3omCABVZR61I3.dVzN0UDL5EzN0czW}: No such file or directory
```
**Flag:** `pwn.college{oFEArUG07-LaHK3omCABVZR61I3.dVzN0UDL5EzN0czW}`
## New Learning
## Reference
