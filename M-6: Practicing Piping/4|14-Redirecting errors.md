# Challenge Description
Just like standard output, you can also redirect the error channel of commands. Here, we'll learn about File Descriptor numbers. A File Descriptor (FD) is a number that describes a communication channel in Linux. You've already been using them, even though you didn't realize it. We're already familiar with three:

  1. FD 0: Standard Input
  2. FD 1: Standard Output
  3. FD 2: Standard Error

When you redirect process communication, you do it by FD number, though some FD numbers are implicit. For example, a > without a number implies 1>, which redirects FD 1 (Standard Output). Thus, the following two commands are equivalent:
```bash
hacker@dojo:~$ echo hi > asdf
hacker@dojo:~$ echo hi 1> asdf
```
Redirecting errors is pretty easy from this point. If you have a command that might produce data via standard error (such as /challenge/run), you can do:
```bash
hacker@dojo:~$ /challenge/run 2> errors.log
```
That will redirect standard error (FD 2) to the errors.log file. Furthermore, you can redirect multiple file descriptors at the same time! For example:
```bash
hacker@dojo:~$ some_command > output.log 2> errors.log
```
That command will redirect output to output.log and errors to errors.log.

Let's put this into practice! In this challenge, you will need to redirect the output of /challenge/run, like before, to myflag, and the "errors" (in our case, the instructions) to instructions. You'll notice that nothing will be printed to the terminal, because you have redirected everything! You can find the instructions/feedback in instructions and the flag in myflag when you successfully pull this off!
# Thought Process & Solution
according our descriptors i redirected the flag output to myflag and errors/instructions to instructions file via FD 2 descriptor. And catted both to verify.
```bash
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag
 
[FLAG] Here is your flag:
[FLAG] pwn.college{wCX5jK5Mi_aXZvAdSqZnwgRhGjQ.ddjN1QDL5EzN0czW}
 
hacker@piping~redirecting-errors:~$ cat instructions
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
```
**Flag:** `pwn.college{}`
## New Learning
## Reference
