# Challenge Description
Now you've learned that process substitution can make command output appear as files for reading with <(command). But you can also use process substitution for writing to commands!

You can duplicate data to two files with tee:
```bash
hacker@dojo:~$ echo HACK | tee THE > PLANET
hacker@dojo:~$ cat THE
HACK
hacker@dojo:~$ cat PLANET
HACK
hacker@dojo:~$
```
And you've used tee to duplicate data to a file and a command:
```bash
hacker@dojo:~$ echo HACK | tee THE | cat
HACK
hacker@dojo:~$ cat THE
HACK
hacker@dojo:~$
```
But what about duplicating to two commands? As tee says in its manpage, it's designed to write to files and to standard output:
```bash
TEE(1)                           User Commands                          TEE(1)

NAME
       tee - read from standard input and write to standard output and files
```
But wait! You just learned that bash can make commands look like files using process substitution! For writing to a command (output process substitution), use >(command). If you write an argument of >(rev), bash will run the rev command (this command reads data from standard input, reverses its order, and writes it to standard output!), but hook up its input to a temporary named pipe file. When commands write to this file, the data goes to the standard input of the command:
```bash
hacker@dojo:~$ echo HACK | rev
KCAH
hacker@dojo:~$ echo HACK | tee >(rev)
HACK
KCAH
```
Above, the following sequence of events took place:

  1. bash started up the rev command, hooking a named pipe (presumably /dev/fd/63) to rev's standard input
  2. bash started up the tee command, hooking a pipe to its standard input, and replacing the first argument to tee with /dev/fd/63. tee never even saw the argument >(rev); the shell substituted it before launching tee
  3. bash used the echo builtin to print HACK into tee's standard input
  4. tee read HACK, wrote it to standard output, and then wrote it to /dev/fd/63 (which is connected to rev's stdin)
  5. rev read HACK from its standard input, reversed it, and wrote KCAH to standard output

Now it's your turn! In this challenge, we have /challenge/hack, /challenge/the, and /challenge/planet. Run the /challenge/hack command, and duplicate its output as input to both the /challenge/the and the /challenge/planet commands! Scroll back through the previous challenges "Duplicating piped data with tee" and "Process substitution for input" if you need a refresher on this method.
# Thought Process & Solution

```bash
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee <(/challenge/the) <(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and 
/challenge/planet. Don't try to copy-paste it; it changes too fast.
272981712477384848
Are you sure you're properly redirecting input into '/challenge/planet'?
Are you sure you're properly redirecting input into '/challenge/the'?
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee <(/challenge/the) | <(/challenge/planet)
bash: /dev/fd/63: Permission denied
Are you sure you're properly redirecting input into '/challenge/the'?
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and 
/challenge/planet. Don't try to copy-paste it; it changes too fast.
15304207222797932386
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{4al5Th-0yLU-rR986hSF8roncf7.dBDO0UDL5EzN0czW}
```
**Flag:** `pwn.college{4al5Th-0yLU-rR986hSF8roncf7.dBDO0UDL5EzN0czW}`
## New Learning
## Reference
