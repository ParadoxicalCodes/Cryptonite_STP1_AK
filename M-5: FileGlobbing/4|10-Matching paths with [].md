# Challenge Description
Globbing happens on a path basis, so you can expand entire paths with your globbed arguments. For example:
```bash
hacker@dojo:~$ touch file_a
hacker@dojo:~$ touch file_b
hacker@dojo:~$ touch file_c
hacker@dojo:~$ ls
file_a	file_b	file_c
hacker@dojo:~$ echo Look: /home/hacker/file_[ab]
Look: /home/hacker/file_a /home/hacker/file_b
```
Now it's your turn. Once more, we've placed a bunch of files in /challenge/files. Starting from your home directory, run /challenge/run with a single argument that bracket-globs into the absolute paths to the file_b, file_a, file_s, and file_h files!
# Thought Process & Solution
Same thing as before this time im not changing my cwd instead the target dir is in my argument for run cmd.
```bash
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{k3m3QaRivz8FJ7OCmZzYcMwwRXk.dRjM4QDL5EzN0czW}
```
**Flag:** `pwn.college{k3m3QaRivz8FJ7OCmZzYcMwwRXk.dRjM4QDL5EzN0czW}`
## New Learning
## Reference
