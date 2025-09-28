# Challenge Description
Some commands, rather than being programs with man pages and help options, are built into the shell itself. These are called builtins. Builtins are invoked just like commands, but the shell handles them internally instead of launching other programs. You can get a list of shell builtins by running the builtin help, as so:
```bash
hacker@dojo:~$ help
```
You can get help on a specific one by passing it to the help builtin. Let's look at a builtin that we've already used earlier, cd!
```bash
hacker@dojo:~$ help cd
cd: cd [-L|[-P [-e]] [-@]] [dir]
    Change the shell working directory.
    
    Change the current directory to DIR.  The default DIR is the value of the
    HOME shell variable.
...
```
Some good information! In this challenge, we'll practice using help to look up help for builtins. This challenge's challenge command is a shell builtin, rather than a program. Like before, you need to lookup its help to figure out the secret value to pass to it!
# Thought Process & Solution
Since we are told challenge is a builtin i call help challenge (this is different from -h we used earlier as thats not built into the shell despite the same name). And we see the argument and secret value, putting them together gives us the flag - initially i ran it like normal /challenge/challenge specifying the path but since its a builtin just like cd i just need to use its name and then pass the argument. Doing this gives us our flag.
```bash
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune        display a fortune
      --version        display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "sPX50ekd".
hacker@man~help-for-builtins:~$ /challenge/challenge --secret sPX50ekd
bash: /challenge/challenge: No such file or directory
hacker@man~help-for-builtins:~$ challenge --secret sPX50ekd
Correct! Here is your flag!
pwn.college{sPX50ekdkBqHamtZjbPCQt78MyJ.dRTM5QDL5EzN0czW}
```
**Flag:** `pwn.college{sPX50ekdkBqHamtZjbPCQt78MyJ.dRTM5QDL5EzN0czW}`
## New Learning
## Reference
