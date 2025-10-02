# Challenge Description
Let's learn to navigate windows in tmux!

Just like screen, tmux has windows. The key combos are different, but the concept is the same:

  - Ctrl-B c - Create a new window
  - Ctrl-B n - Next window
  - Ctrl-B p - Previous window
  - Ctrl-B 0 through Ctrl-B 9 - Jump to window 0-9
  - Ctrl-B w - See a nice window picker

Tmux shows your windows at the bottom in a status bar that looks like:
```bash
[0] 0:bash* 1:bash
```
The * shows your current window, and each entry also shows the process that the window was created to run.

We've created a tmux session with two windows:

  - Window 0 has the flag!
  - Window 1 has your warm welcome.

Go get that flag!
# Thought Process & Solution

[Main terminal]
```bash
hacker@terminal-multiplexing~switching-windows-tmux:~$ tmux ls
challenge_session: 2 windows (created Thu Oct  2 05:59:13 2025)
hacker@terminal-multiplexing~switching-windows-tmux:~$ tmux a
```
[Window 1]
```
 cat <<MSG
Welcome to the tmux window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-B 0 to switch to window 0!
MSG
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Welcome to the tmux window switching challenge!
> You are currently in window 1.
> The flag is hidden in window 0.
> Use Ctrl-B 0 to switch to window 0!
> MSG
Welcome to the tmux window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-B 0 to switch to window 0!
```
[Window 0]
```
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{k40QwWvMZhqXMxMR62_tsqiCFsM.QXwkjM4EDL5EzN0czW}> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{k40QwWvMZhqXMxMR62_tsqiCFsM.QXwkjM4EDL5EzN0czW}
```
**Flag:** `pwn.college{k40QwWvMZhqXMxMR62_tsqiCFsM.QXwkjM4EDL5EzN0czW}`
## New Learning
## Reference
