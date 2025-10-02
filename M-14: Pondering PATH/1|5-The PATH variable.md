# Challenge Description
It turns out that the answer to "How does the shell find ls?" is fairly simple. There is a special shell variable, called PATH, that stores a bunch of directory paths in which the shell will search for programs corresponding to commands. If you blank out the variable, things go badly:
```bash
hacker@dojo:~$ ls
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$ PATH=""
hacker@dojo:~$ ls
bash: ls: No such file or directory
hacker@dojo:~$
```
Without a PATH, bash cannot find the ls command.

In this level, you will disrupt the operation of the /challenge/run program. This program will DELETE the flag file using the rm command. However, if it can't find the rm command, the flag will not be deleted, and the challenge will give it to you! Thus, you must make it so that /challenge/run also can't find the rm command!

Keep in mind: /challenge/run will be a child process of your shell, so you must apply the concepts you learned in Shell Variables to mess with its PATH variable! If you don't succeed, and the flag gets deleted, you will need to restart the challenge to try again!
# Thought Process & Solution

```bash

```
**Flag:** `pwn.college{}`
## New Learning
PATH is an environmental variable in Linux and other Unix-like operating systems that tells the shell which directories to search for executable files (i.e., ready-to-run programs) in response to commands issued by a user. It increases both the convenience and the safety of such operating systems and is widely considered to be the single most important environmental variable.

A user's PATH consists of a series of colon-separated absolute paths that are stored in plain text files. Whenever a user types in a command at the command line that is not built into the shell or that does not include its absolute path and then presses the Enter key, the shell searches through those directories, which constitute the user's search path, until it finds an executable file with that name.

The concentrating by default of most executable files in just a few directories rather than spread all over the filesystem and the use of the PATH variable to find them eliminates the need for users to remember which directories they are in and to type their absolute path names. That is, any such program can be run by merely typing its name, such as ls instead of /bin/ls and head instead of /usr/bin/head, regardless of where the user is currently working on the filesystem. This also greatly reduces the possibility of damage to data or even to the system as a whole from the accidental running of a script that has the same name as a standard command.1

A list of all the current environmental variables and their values for the current user, including all the directories in the PATH variable, can be seen by running the env command without any options or arguments (i.e., input data), i.e.,

```env```

As there can be considerable output, it can be convenient to modify this command so that it displays just the PATH environmental variable and its value. This can be accomplished by using a pipe (represented by the vertical bar character) to transfer the output of env to the grep filter and use PATH as an argument to grep, i.e.,

```env | grep PATH```

Another way to view the contents of just PATH alone is by using the echo command with $PATH as an argument:

```echo $PATH```

echo repeats on the display screen whatever follows it on the command line. The dollar sign immediately preceding PATH tells echo to repeat the value of the variable PATH rather than its name.
## Reference
[What is PATH?](https://www.linfo.org/path_env_var.html)
