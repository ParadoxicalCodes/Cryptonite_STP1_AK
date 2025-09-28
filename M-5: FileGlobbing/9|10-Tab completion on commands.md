# Challenge Description
Tab completion is for more than files! You can also tab-complete commands. This level has a command that starts with pwncollege, and it'll give you the flag. Type pwncollege and hit the tab key to auto-complete it!

NOTE: You can auto-complete any command, but be careful: callous auto-completes without double-checking the result can wreak havoc in your shell if you accidentally run the wrong commands!
# Thought Process & Solution
As an experiment i decided to tab after typing just p, which gave us 179 possibilities! obviously i dont need all of them my only concern is just with pwncollege. So after writing pwn then tab then chose pwncollege-954 and running this gave our flag.
```bash
hacker@globbing~tab-completion-on-commands:~$ p
Display all 179 possibilities? (y or n)
hacker@globbing~tab-completion-on-commands:~$ p
bash: p: command not found
hacker@globbing~tab-completion-on-commands:~$ pwn
pwn             pwncollege-954  pwndbg          pwnstrip        pwntools-gdb    
hacker@globbing~tab-completion-on-commands:~$ pwncollege-954
Correct! Here is your flag:
pwn.college{Md7Xz_gexAng5XChcg5qAmjpXxC.QX1QTM3EDL5EzN0czW}
```
**Flag:** `pwn.college{}`
## New Learning
## Reference
