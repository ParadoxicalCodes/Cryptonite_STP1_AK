# Challenge Description
You've learned how to make shell scripts, but so far they've just been lists of commands. Scripts become much more powerful when they can accept arguments! This might look like:
```bash
hacker@dojo:~$ bash myscript.sh hello world
```
The script can access these arguments using special variables:

  $1 contains the first argument ("hello")
  $2 contains the second argument ("world")
  $3 would contain the third argument (if there had been one)
...and so on
Here's a simple example:
```bash
hacker@dojo:~$ cat myscript.sh
#!/bin/bash
echo "First argument: $1"
echo "Second argument: $2"
hacker@dojo:~$ bash myscript.sh hello world
First argument: hello
Second argument: world
hacker@dojo:~$
```
For this challenge, you need to write a script at /home/hacker/solve.sh that:

  1. Takes two arguments
  2. Outputs them in REVERSE order (second argument first, then the first argument)

For example:
```bash
hacker@dojo:~$ bash /home/hacker/solve.sh pwn college
college pwn
hacker@dojo:~$
```
Once your script works correctly, run /challenge/run to get your flag!
# Thought Process & Solution

```bash
hacker@chaining~scripting-with-arguments:~$ nano ~/solve.sh
hacker@chaining~scripting-with-arguments:~$ cat ~/solve.sh
#!/bin/bash

val1=$1
val2=$2
echo "$val2 $val1"
hacker@chaining~scripting-with-arguments:~$ bash ~/solve.sh pwn college
college pwn
hacker@chaining~scripting-with-arguments:~$ bash ~/solve.sh hi hello
hello hi
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{8hfuE5KXHODGdhkKGPIexOdKrNd.QX1MzM4EDL5EzN0czW}
```
**Flag:** `pwn.college{8hfuE5KXHODGdhkKGPIexOdKrNd.QX1MzM4EDL5EzN0czW}`
## New Learning
## Reference
