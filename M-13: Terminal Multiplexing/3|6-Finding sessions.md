# Challenge Description
Time for some screen detective work!

If you become an avid screen user, you will inevitably end up with multiple sessions running. How do you find the right one to reattach to?

Well, we can list them:
```bash
hacker@dojo:~$ screen -ls
There are screens on:
        23847.mysession   (Detached)
        23851.goodwork    (Detached)
        23855.morework    (Detached)
3 Sockets in /run/screen/S-hacker.
```
The identifiers of the sessions are the PID of each respective screen process, a dot, and the name of the screen session. To attach to a specific one, you use its name or its PID by giving it as an argument to screen -r.
```bash
hacker@dojo:~$ screen -r goodwork
```
In this challenge, we've created three screen sessions for you. One of them contains the flag. The other two are decoys!

You'll need to check each one until you find it. Don't forget to detach (Ctrl-A d) before trying the next session!
# Thought Process & Solution

```bash
hacker@terminal-multiplexing~finding-sessions:~$ screen -ls
There are screens on:
	166.pts-0.terminal-multiplexing~detaching-and-attaching	(Remote or dead)
	201.pts-0.terminal-multiplexing~detaching-and-attaching	(Remote or dead)
	145.pts-0.terminal-multiplexing~detaching-and-attaching	(Remote or dead)
	144.session_cdbfafa436b27415	(Remote or dead)
	147.session_5f323584a9c40519	(Remote or dead)
	150.session_a4a19f17111e3d64	(Remote or dead)
	144.session_13ec4baa0fcd05c7	(Detached)
	147.session_74e49636d52133bf	(Detached)
	150.session_beaaab28b72115d9	(Detached)
9 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 150
Remove dead screens with 'screen -wipe'.
[detached from 150.session_beaaab28b72115d9]
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 147
Remove dead screens with 'screen -wipe'.
[detached from 147.session_74e49636d52133bf]
```
[Screen 150]
```
hacker@terminal-multiplexing~finding-sessions:~$  echo 'Wrong session! Keep looking.'
Wrong session! Keep looking.
```
[Screen 147]
```
hacker@terminal-multiplexing~finding-sessions:~$  echo 'Congratulations! You found the right session!'
Congratulations! You found the right session!
hacker@terminal-multiplexing~finding-sessions:~$  echo pwn.college{sDzSJwmjRl2-oF89fZiBKwb8FLp.QX3gjM4EDL5EzN0czW}
pwn.college{sDzSJwmjRl2-oF89fZiBKwb8FLp.QX3gjM4EDL5EzN0czW}
```
**Flag:** `pwn.college{}`
## New Learning
## Reference
