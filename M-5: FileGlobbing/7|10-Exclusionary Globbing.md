# Challenge Description
Sometimes, you want to filter out files in a glob! Luckily, [] helps you do just this. If the first character in the brackets is a ! or (in newer versions of bash) a ^, the glob inverts, and that bracket instance matches characters that aren't listed. For example:
```bash
hacker@dojo:~$ touch file_a
hacker@dojo:~$ touch file_b
hacker@dojo:~$ touch file_c
hacker@dojo:~$ ls
file_a	file_b	file_c
hacker@dojo:~$ echo Look: file_[!ab]
Look: file_c
hacker@dojo:~$ echo Look: file_[^ab]
Look: file_c
hacker@dojo:~$ echo Look: file_[ab]
Look: file_a file_b
```
Armed with this knowledge, go forth to /challenge/files and run /challenge/run with all files that don't start with p, w, or n!

NOTE: The ! character has a different special meaning in bash when it's not the first character of a [] glob, so keep that in mind if things stop making sense! ^ does not have this problem, but is also not compatible with older shells.
# Thought Process & Solution
Same logic as before but this time we are supposed to exclude the results that match so we use "!" inside the brackets to achieve that.
```bash
hacker@globbing~exclusionary-globbing:~$ cd /c*/f*
hacker@globbing~exclusionary-globbing:/challenge/files$ /c*/r* [!pwn]*
You got it! Here is your flag!
pwn.college{U80ErmBFJa9_SlN1_83o14xH_j-.dZjM4QDL5EzN0czW}
```
**Flag:** `pwn.college{}`
## New Learning
## Reference
