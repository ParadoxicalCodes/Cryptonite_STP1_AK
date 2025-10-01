# Challenge Description
You have learned to interrupt processes with Ctrl-C, but there are less drastic measures you can use to get your terminal back! You can suspend processes to the background with Ctrl-Z. In this level, we'll explore how this works and, in the next level, we'll figure out how to resume those suspended processes!

This level's run wants to see another copy of itself running and using the same terminal. How? Use the terminal to launch it, then suspend it, then launch another copy while the first is suspended!
# Thought Process & Solution

```bash
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         163     135  0 12:47 pts/0    00:00:00 bash /challenge/run
root         165     163  0 12:47 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         163     135  0 12:47 pts/0    00:00:00 bash /challenge/run
root         170     135  0 12:47 pts/0    00:00:00 bash /challenge/run
root         172     170  0 12:47 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{g8t2dkNYKDuQ4ZXQlw1G2rnmD1i.dVDN4QDL5EzN0czW}
```
**Flag:** `pwn.college{g8t2dkNYKDuQ4ZXQlw1G2rnmD1i.dVDN4QDL5EzN0czW}`
## New Learning
## Reference
