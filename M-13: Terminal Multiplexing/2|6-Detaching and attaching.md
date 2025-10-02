# Challenge Description

Now we'll start digging in with the magic of detaching!

Imagine you're working on something important over a remote connection, and your connection drops. With a normal terminal (outside of this awesome dojo environment), everything's gone. With screen, your work keeps running, and you can reattach later!

You can also detach on purpose, which we'll do in this challenge. You detach by pressing Ctrl-A, followed by d (for detach). This leaves your session running in the background while you return to your normal terminal.
```bash
hacker@dojo:~$ screen
[doing some work...]
[Press Ctrl-A, then d]
[detached from 12345.pts-0.hostname]
hacker@dojo:~$ 
```
To reattach, you can use the -r argument to screen:
```bash
hacker@dojo:~$ screen -r
```
For this challenge, you'll need to:

  1. Launch screen
  2. Detach from it.
  3. Run /challenge/run (this will secretly send the flag to your detached session!)
  4. Reattach to see your prize

FUN FACT: Ctrl-A is screen's activation key for all of its shortcuts in its default configuration. All screen functionality is activated by some command combination starting with Ctrl-A.

HINT: Remember: Hold Ctrl and press A, then release both and press d.

HINT: If you see [detached from...], you did it right!
# Thought Process & Solution


[Main terminal]
```bash
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen
[detached from 201.pts-0.terminal-multiplexing~detaching-and-attaching]
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 166.pts-0.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:

  screen -r

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
```
[Screen]
```
hacker@terminal-multiplexing~detaching-and-attaching:~$
hacker@terminal-multiplexing~detaching-and-attaching:~$ echo Yes! Flag is: pwn.college{g2a8dvDG4tJVhEHUZuXvUbntYfI.QX2gjM4EDL5EzN0czW}
Yes! Flag is: pwn.college{g2a8dvDG4tJVhEHUZuXvUbntYfI.QX2gjM4EDL5EzN0czW}
```
**Flag:** `pwn.college{}`
## New Learning
## Reference
