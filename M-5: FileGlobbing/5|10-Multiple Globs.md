# Challenge Description
So far, you've specified one glob at a time, but you can do more! Bash supports the expansion of multiple globs in a single word. For example:
```bash
hacker@dojo:~$ cat /*fl*
pwn.college{YEAH}
hacker@dojo:~$
```
What happens above is that the shell looks for all files in / that start with anything (including nothing), then have an f and an l, and end in anything (including ag, which makes flag).

Now you try it. We put a few happy, but diversely-named files in /challenge/files. Go cd there and run /challenge/run, providing a single argument: a short (3 characters or less) globbed word with two * globs in it that covers every word that contains the letter p.
# Thought Process & Solution
I first passed p** as the argument but its wrong as it searches for everything starting with p, but we want to search before p and after p also hence "* p *" works.
```bash
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run p**
Your expansion did not expand to the requested files (happy optimistic pwning 
splendid uplifting).
Instead, it expanded to:
pwning
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{0wdky6eRCvIKZcnaaoVoxBgEqsM.QXycTO2EDL5EzN0czW}
```
**Flag:** `pwn.college{0wdky6eRCvIKZcnaaoVoxBgEqsM.QXycTO2EDL5EzN0czW}`
## New Learning
## Reference
