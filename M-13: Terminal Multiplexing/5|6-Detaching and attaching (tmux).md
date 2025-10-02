# Challenge Description
Let's try the same thing with tmux!

tmux (terminal multiplexer) is screen's younger, more modern cousin. It does all the same things but with some different key bindings. The biggest difference? Instead of Ctrl-A, tmux uses Ctrl-B as its command prefix.

So to detach from tmux, you press Ctrl-B followed by d.
```bash
hacker@dojo:~$ tmux
[doing some work...]
[Press Ctrl-B, then d]
[detached (from session 0)]
hacker@dojo:~$ 
```
The commands also differ:

  - tmux ls - List sessions
  - tmux attach or tmux a - Reattach to session

For this challenge:

  1. Launch tmux
  2. Detach from it.
  3. Run /challenge/run (this will send the flag to your detached session!)
  4. Reattach to see your prize
# Thought Process & Solution

[Main terminal]
```bash
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Found detached tmux session: 0
Sending flag to your tmux session...

Flag sent! Now reattach to your tmux session with:
  tmux attach

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux a
```
[tmux screen]
```
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$  echo Congratulations, here is your flag: pwn.college{cpUd_U_Ld6_y1zI67kd_G-OuBFz.QX5gjM4EDL5EzN0czW}
Congratulations, here is your flag: pwn.college{cpUd_U_Ld6_y1zI67kd_G-OuBFz.QX5gjM4EDL5EzN0czW}
```
**Flag:** `pwn.college{}`
## New Learning
## Reference
