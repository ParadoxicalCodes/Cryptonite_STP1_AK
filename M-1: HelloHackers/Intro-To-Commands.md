# Intro to Commands
In this challenge, you will invoke your first command! When you type a command and hit enter, the command will be invoked, as so:
```
hacker@dojo:~$ whoami
hacker
hacker@dojo:~$
```
## Thought Process & Solution
Not much to say for this challenge - typing in hello in the cli gave us the flag, though in the process I do see that commands are case sensitive.
```Bash
hacker@hello~intro-to-commands:~$ Hello
bash: Hello: command not found
hacker@hello~intro-to-commands:~$ hello
Success! Here is your flag:
pwn.college{gbngfatLMp3VrXlNXfxbbQtsJ0g.ddjNyUDL5EzN0czW}
```
**Flag:** `pwn.college{gbngfatLMp3VrXlNXfxbbQtsJ0g.ddjNyUDL5EzN0czW}`
