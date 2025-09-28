# Challenge Description

Some programs don't have a man page, but might tell you how to run them if invoked with a special argument. Usually, this argument is --help, but it can often be -h or, in rare cases, -?, help, or other esoteric values like /? (though that latter is more frequently encountered on Windows).

In this level, you will practice reading a program's documentation with --help. Try it out!
# Thought Process & Solution
The only mistake i committed here was that i thought i could run -h with just cmd name (challenge -h  -> similar to what we do in man) but here i have to actually specify the whole cmd path then do -h.

So doing /challenge/challenge -h gives us the help output and from there i see two arguments of note which is -p and -g. Doing them in succession gives us all the necessary info to get the flag.
```bash
hacker@man~helpful-programs:~$ challenge -h
bash: challenge: command not found
hacker@man~helpful-programs:~$ /challenge/challenge -h
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG]
                                            [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the
                        flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 175
hacker@man~helpful-programs:~$ /challenge/challenge -g 175
Correct usage! Your flag: pwn.college{MTZbqC1SQoTPK_z75qnBedmCQNX.ddjM4QDL5EzN0czW}
```
**Flag:** `pwn.college{MTZbqC1SQoTPK_z75qnBedmCQNX.ddjM4QDL5EzN0czW}`
## New Learning
## Reference
