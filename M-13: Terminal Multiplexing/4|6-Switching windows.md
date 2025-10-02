# Challenge Description
Okay, so far, screen is just a weird sort of terminal-with-a-terminal. But it can be much more!

Inside a single screen session, you can have multiple windows, like your browser has multiple tabs. This can be super handy for organizing different tasks!

These windows are handled with different keyboard shortcuts, all starting with Ctrl-A:

  - Ctrl-A c - Create a new window
  - Ctrl-A n - Next window
  - Ctrl-A p - Previous window
  - Ctrl-A 0 through Ctrl-A 9 - Jump directly to window 0-9
  - Ctrl-A " - bring up a selection menu of all of the windows

For this challenge, we've set up a screen session with two windows:

  - Window 0 has... well, you'll have to switch there to find out!
  - Window 1 has a welcome message

Attach to the session with screen -r, then use one of the key combinations above to switch to Window 1. Go get that flag!
# Thought Process & Solution

[Main terminal]
```bash
hacker@terminal-multiplexing~switching-windows:~$ screen -ls
There are screens on:
	166.pts-0.terminal-multiplexing~detaching-and-attaching	(Remote or dead)
	201.pts-0.terminal-multiplexing~detaching-and-attaching	(Remote or dead)
	145.pts-0.terminal-multiplexing~detaching-and-attaching	(Remote or dead)
	144.session_cdbfafa436b27415	(Remote or dead)
	147.session_5f323584a9c40519	(Remote or dead)
	150.session_a4a19f17111e3d64	(Remote or dead)
	144.session_13ec4baa0fcd05c7	(Remote or dead)
	147.session_74e49636d52133bf	(Remote or dead)
	150.session_beaaab28b72115d9	(Remote or dead)
	135.challenge_session	(Detached)
10 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~switching-windows:~$ screen -r 135
```
[Window 1]
```bash
 cat <<MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
MSG
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Welcome to the window switching challenge!
> You are currently in window 1.
> The flag is hidden in window 0.
> Use Ctrl-A 0 to switch to window 0!
> MSG
Welcome to the window switching challenge!
You are currently in window 1.
The flag is hidden in window 0.
Use Ctrl-A 0 to switch to window 0!
```
[Window 0]
```bash
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{kfqjsMVLxQXw6C6zlp3SXqyNuSL.QX4gjM4EDL5EzN0czW}> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{kfqjsMVLxQXw6C6zlp3SXqyNuSL.QX4gjM4EDL5EzN0czW}
```
**Flag:** `pwn.college{kfqjsMVLxQXw6C6zlp3SXqyNuSL.QX4gjM4EDL5EzN0czW}`
## New Learning
## Reference
