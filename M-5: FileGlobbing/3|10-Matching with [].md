# Challenge Description

Next, we will cover []. The square brackets are, essentially, a limited form of ?, in that instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets. For example, [pwn] will match the character p, w, or n. For example:
```bash
hacker@dojo:~$ touch file_a
hacker@dojo:~$ touch file_b
hacker@dojo:~$ touch file_c
hacker@dojo:~$ ls
file_a	file_b	file_c
hacker@dojo:~$ echo Look: file_[ab]
Look: file_a file_b
```
Try it here! We've placed a bunch of files in /challenge/files. Change your working directory to /challenge/files and run /challenge/run with a single argument that bracket-globs into file_b, file_a, file_s, and file_h!
# Thought Process & Solution
I first changed my cwd to /challenge/files and then did /challenge/run with bracket glob [bash] as argument but it seems i was to run this cmd from ~. (Slightly confused because the desc says otherwise).
```bash
hacker@globbing~matching-paths-with-:~$ cd /challenge/files
hacker@globbing~matching-paths-with-:/challenge/files$ /challenge/run /challenge/files/file_[bash]
Error: please run with a working directory of /home/hacker!
hacker@globbing~matching-paths-with-:/challenge/files$ cd
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{k3m3QaRivz8FJ7OCmZzYcMwwRXk.dRjM4QDL5EzN0czW}
```
**Flag:** `pwn.college{k3m3QaRivz8FJ7OCmZzYcMwwRXk.dRjM4QDL5EzN0czW}`
## New Learning
## Reference
