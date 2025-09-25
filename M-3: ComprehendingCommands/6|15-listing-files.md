# Challenge Description
So far, we've told you which files to interact with. But directories can have lots of files (and other directories) inside them, and we won't always be here to tell you their names. You'll need to learn to list their contents using the ls command!

ls will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided. Observe:
```bash
hacker@dojo:~$ ls /challenge
run
hacker@dojo:~$ ls
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$ ls /home/hacker
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$
```
In this challenge, we've named /challenge/run with some random name! List the files in /challenge to find it.
# Thought Process & Solution
i did ls first to see if challenge dir is there or not (not visible ?). I still move to /challenge as mentioned in the description and doing ls again shows us our renamed run file. Now i just execute it to get my flag.
```bash
hacker@commands~listing-files:~$ ls
COLLEGE  a.sh            flaggg.txt    myflag      pwn         t    the-flag
Desktop  cd              instructions  output.txt  pwn_output  tee  x.sh
PWN      college_output  leap          planet      rm          the
hacker@commands~listing-files:~$ cd /challenge
hacker@commands~listing-files:/challenge$ ls
31133-renamed-run-16281  DESCRIPTION.md
hacker@commands~listing-files:/challenge$ 31133-renamed-run-16281
bash: 31133-renamed-run-16281: command not found
hacker@commands~listing-files:/challenge$ ./31133-renamed-run-16281
Yahaha, you found me! Here is your flag:
pwn.college{M0-jsvxIVnVeMgkPi_EyaU8j2Ck.dhjM4QDL5EzN0czW}
```
**Flag:** `pwn.college{M0-jsvxIVnVeMgkPi_EyaU8j2Ck.dhjM4QDL5EzN0czW}`
## New Learning
## Reference
