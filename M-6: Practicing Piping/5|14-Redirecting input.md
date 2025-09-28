# Challenge Description
Just like you can redirect output from programs, you can redirect input to programs! This is done using <, as so:
```bash
hacker@dojo:~$ echo yo > message
hacker@dojo:~$ cat message
yo
hacker@dojo:~$ rev < message
oy
```
You can do interesting things with a lot of different programs using input redirection! In this level, we will practice using /challenge/run, which will require you to redirect the PWN file to it and have the PWN file contain the value COLLEGE! To write that value to the PWN file, recall the prior challenge on output redirection from echo!
# Thought Process & Solution
I first echoed COLLEGE to PWN then redirected PWN to our cmd which gave us the flag.
```bash
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{Qm8s9N4_0s1VygmISmlZW0yQGEr.dBzN1QDL5EzN0czW}
```
**Flag:** `pwn.college{}`
## New Learning
## Reference
