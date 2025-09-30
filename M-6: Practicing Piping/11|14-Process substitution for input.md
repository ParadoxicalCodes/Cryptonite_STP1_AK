# Challenge Description
Sometimes you need to compare the output of two commands rather than two files. You might think to save each output to a file first:
```bash
hacker@dojo:~$ command1 > file1
hacker@dojo:~$ command2 > file2
hacker@dojo:~$ diff file1 file2
```
But there's a more elegant way! Linux follows the philosophy that "everything is a file". That is, the system strives to provide file-like access to most resources, including the input and output of running programs! The shell follows this philosophy, allowing you to, for example, use any utility that takes file arguments on the command line and hook it up to the output of programs, as you learned in the previous few levels.

Interestingly, we can go further, and hook input and output of programs to arguments of commands. This is done using Process Substitution. For reading from a command (input process substitution), use <(command). When you write <(command), bash will run the command and hook up its output to a temporary file that it will create. This isn't a real file, of course, it's what's called a named pipe, in that it has a file name:
```bash
hacker@dojo:~$ echo <(echo hi)
/dev/fd/63
hacker@dojo:~$
```
Where did /dev/fd/63 come from? bash replaced <(echo hi) with the path of the named pipe file that's hooked up to the command's output! While the command is running, reading from this file will read data from the standard output of the command. Typically, this is done using commands that take input files as arguments:
```bash
hacker@dojo:~$ cat <(echo hi)
hi
hacker@dojo:~$
```
Of course, you can specify this multiple times:
```bash
hacker@dojo:~$ echo <(echo pwn) <(echo college)
/dev/fd/63 /dev/fd/64
hacker@dojo:~$ cat <(echo pwn) <(echo college)
pwn
college
hacker@dojo:~$
```
Now for your challenge! Recall what you learned in the diff challenge from Comprehending Commands. In that challenge, you diffed two files. Now, you'll diff two sets of command outputs: /challenge/print_decoys, which will print a bunch of decoy flags, and /challenge/print_decoys_and_flag which will print those same decoys plus the real flag.

Use process substitution with diff to compare the outputs of these two programs and find your flag!
# Thought Process & Solution

```bash
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
28a29
> pwn.college{8uU3R2-tYx1BEKbCja3P7sYCczd.QX2AzM4EDL5EzN0czW}
```
**Flag:** `pwn.college{8uU3R2-tYx1BEKbCja3P7sYCczd.QX2AzM4EDL5EzN0czW}`
## New Learning
## Reference
