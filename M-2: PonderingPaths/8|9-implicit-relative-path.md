# Challenge Description
In this level, we'll practice referring to paths using . a bit more. This challenge will need you to run it from the /challenge directory. Here, things get slightly tricky.

Linux explicitly avoids automatically looking in the current directory when you provide a "naked" path. Consider the following:
```bash
hacker@dojo:~$ cd /challenge
hacker@dojo:/challenge$ run
```
This will not invoke /challenge/run. This is actually a safety measure: if Linux searched the current directory for programs every time you entered a naked path, you could accidentally execute programs in your current directory that happened to have the same names as core system utilities! As a result, the above commands will yield the following error:
```bash
bash: run: command not found
```
We'll explore the mechanisms behind this concept later, but in this challenge, we'll learn how to explicitly use relative paths to launch run in this scenario. The way to do this is to tell Linux that you explicitly want to execute a program in the current directory, using . like in the previous levels. Give it a try now!
# Thought Process & Solution
Made an incorrect cmd so as to get instructions or hints, then acc to instructions i went moved to /challenge dir. And since /run is not possible directly we are supposed to call it implicitly using ".", so single dot refers to cwd and double dot would refer to prev dir.
```bash
hacker@paths~implicit-relative-path:~$ /challenge/run
Incorrect...
You are not currently in the /challenge directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{oR881_ddVF1LxySvKp-5ujGZZlp.dFTN1QDL5EzN0czW}
hacker@paths~implicit-relative-path:/challenge$ ./challenge/run
bash: ./challenge/run: No such file or directory
hacker@paths~implicit-relative-path:/challenge$ ../challenge/run
Correct!!!
../challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{oR881_ddVF1LxySvKp-5ujGZZlp.dFTN1QDL5EzN0czW}
```
**Flag:** `pwn.college{oR881_ddVF1LxySvKp-5ujGZZlp.dFTN1QDL5EzN0czW}`
## New Learning
## Reference
