# Challenge Description
Let's try something a bit trickier! You've piped output between programs with |, but so far, this has just been between one command's output and a different command's input. But what if you wanted to send the output of several programs to one command? There are a few ways to do this, and we'll explore a simple one here: redirecting output from your script!

As far as the shell is concerned, your script is just another command. That means you can redirect its input and output just like you did for commands in the Piping module! For example, you can write it to a file:
```bash
hacker@dojo:~$ cat script.sh
echo PWN
echo COLLEGE
hacker@dojo:~$ bash script.sh > output
hacker@dojo:~$ cat output
PWN
COLLEGE
hacker@dojo:~$
```
All of the various redirection methods work: > for stdout, 2> for stderr, < for stdin, >> and 2>> for append-mode redirection, >& for redirecting to other file descriptors, and | for piping to another command.

In this level, we will practice piping (|) from your script to another program. Like before, you need to create a script that calls the /challenge/pwn command followed by the /challenge/college command, and pipe the output of the script into a single invocation of the /challenge/solve command!
# Thought Process & Solution

```bash
hacker@chaining~redirecting-script-output:~$ ls
COLLEGE  a.sh            flaggg.txt    myflag        output.txt  pwn_output  tee       x.sh
Desktop  cd              instructions  need.txt      planet      rm          the
PWN      college_output  leap          not-the-flag  pwn         t           the-flag
hacker@chaining~redirecting-script-output:~$ cat a.sh
/challenge/solve
hacker@chaining~redirecting-script-output:~$ cat x.sh
/challenge/pwn; /challenge/college
hacker@chaining~redirecting-script-output:~$ bash x.sh > /challenge/solve
No shenanigans with bash options yet, please! Just run your script with 'bash 
x.sh'.
bash: /challenge/solve: Permission denied
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{kOWvYvhSxxliU7evF2H21-u8_41.dhTM5QDL5EzN0czW}
```
**Flag:** `pwn.college{kOWvYvhSxxliU7evF2H21-u8_41.dhTM5QDL5EzN0czW}`
## New Learning
## Reference
