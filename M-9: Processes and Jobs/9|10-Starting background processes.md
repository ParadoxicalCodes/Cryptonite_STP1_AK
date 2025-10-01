# Challenge Description
Of course, you don't have to suspend processes to background them: you can start them backgrounded right off the bat! It's easy; all you have to do is append a & to the command, like so:
```bash
hacker@dojo:~$ sleep 1337 &
[1] 1771
hacker@dojo:~$ ps -o user,pid,stat,cmd
USER         PID STAT CMD
hacker      1709 Ss   bash
hacker      1771 S    sleep 1337
hacker      1782 R+   ps -o user,pid,stat,cmd
hacker@dojo:~$ 
```
Here, sleep is actively running in the background, not suspended. Now it's your turn to practice! Launch /challenge/run backgrounded for the flag!
# Thought Process & Solution

```bash
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 163
hacker@processes~starting-backgrounded-processes:~$ 


Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{UfYE0azlo_sZaa8Mhkpr9hFD97l.dlDN4QDL5EzN0czW}

[1]+  Done                    /challenge/run
```
**Flag:** `pwn.college{UfYE0azlo_sZaa8Mhkpr9hFD97l.dlDN4QDL5EzN0czW}`
## New Learning
## Reference
