# Challenge Description
When you type the name of a command, something inside one of the many directories listed in your $PATH variable is what actually gets executed (of course, unless the command is a builtin!). But which file, precisely? You can find out with the aptly-named which command:
```bash
hacker@dojo:~$ which cat
/bin/cat
hacker@dojo:~$ /bin/cat /flag
YEAH
hacker@dojo:~$
```
Mirroring what the shell does when searching for commands, which looks at each directory in $PATH in order and prints the first file it finds whose name matches the argument you passed.

In this challenge, we added a win command somewhere in your $PATH, but it won't give you the flag. Instead, it's in the same directory as a flag file that we made readable by you! You must find win (with the which command), and cat the flag out of that directory!
# Thought Process & Solution

```bash
hacker@path~finding-commands:~$ echo $PATH
/run/challenge/bin:/run/dojo/bin:/bin:/challenge/paths/12401:/challenge/paths/19438:/challenge/paths/4779:/challenge/paths/18280:/challenge/paths/15185:/challenge/paths/24053:/challenge/paths/1380:/challenge/paths/7674:/challenge/paths/15397:/challenge/paths/25269:/challenge/paths/24336:/challenge/paths/14035:/challenge/paths/29652:/challenge/paths/32106:/challenge/paths/27817:/challenge/paths/26908:/challenge/paths/22315:/challenge/paths/1768:/challenge/paths/5405:/challenge/paths/9316:/challenge/paths/13328:/challenge/paths/12531:/challenge/paths/12993:/challenge/paths/22695:/challenge/paths/16554:/challenge/paths/358:/challenge/paths/21551:/challenge/paths/1867:/challenge/paths/22761:/challenge/paths/23079:/challenge/paths/24951:/challenge/paths/21556:/challenge/paths/24792:/challenge/paths/6807:/challenge/paths/14698:/challenge/paths/2598:/challenge/paths/28048:/challenge/paths/10465:/challenge/paths/23940:/challenge/paths/11964:/challenge/paths/29564:/challenge/paths/29124:/challenge/paths/4668:/challenge/paths/22759:/challenge/paths/23614:/challenge/paths/5618:/challenge/paths/29220:/challenge/paths/13024:/challenge/paths/9567:/challenge/paths/4106:/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
hacker@path~finding-commands:~$ which win
/challenge/paths/29124/win
hacker@path~finding-commands:~$ ls /challenge/paths/29124/win
/challenge/paths/29124/win
hacker@path~finding-commands:~$ /challenge/paths/29124/win
Search for the flag in the same directory in which I am located!
hacker@path~finding-commands:~$ ls -l /challenge/paths/29124/win
-rwsr-xr-x 1 root root 97 Jun  6 11:37 /challenge/paths/29124/win
hacker@path~finding-commands:~$ cat /challenge/paths/29124/win
#!/bin/bash

/bin/fold -s <<< "Search for the flag in the same directory in which I am located!"
hacker@path~finding-commands:~$ file /challenge/paths/29124/win
/challenge/paths/29124/win: setuid Bourne-Again shell script, ASCII text executable
hacker@path~finding-commands:~$ ls -l /challenge/paths/29124
total 8
-rw-r--r-- 1 root root 60 Oct  2 06:31 flag
-rwsr-xr-x 1 root root 97 Jun  6 11:37 win
hacker@path~finding-commands:~$ /challenge/paths/29124/flag
bash: /challenge/paths/29124/flag: Permission denied
hacker@path~finding-commands:~$ cat /challenge/paths/29124/flag
pwn.college{47XimCwm_XGbMv6Z7rLiTG7p-gO.QX3MTM3EDL5EzN0czW}
```
**Flag:** `pwn.college{47XimCwm_XGbMv6Z7rLiTG7p-gO.QX3MTM3EDL5EzN0czW}`
## New Learning
## Reference
