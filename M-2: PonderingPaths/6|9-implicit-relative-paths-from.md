# Challenge Description
Now you're familiar with the concept of referring to absolute paths and changing directories. If you put in absolute paths everywhere, then it really doesn't matter what directory you are in, as you likely found out in the previous three challenges.

However, the current working directory does matter for relative paths.

A relative path is any path that does not start at root (i.e., it does not start with /).
A relative path is interpreted relative to your current working directory (cwd).
Your cwd is the directory that your prompt is currently located at.
This means how you specify a particular file, depends on where the terminal prompt is located.

Imagine we want to access some file located at /tmp/a/b/my_file.

If my cwd is /, then a relative path to the file is tmp/a/b/my_file.
If my cwd is /tmp, then a relative path to the file is a/b/my_file.
If my cwd is /tmp/a/b/c, then a relative path to the file is ../my_file. The .. refers to the parent directory.
Let's try it here! You'll need to run /challenge/run using a relative path while having a current working directory of /. For this level, I'll give you a hint. Your relative path starts with the letter c 😊
# Thought Process & Solution
We have been doing /challenge/run from our root dir where our cwd was "~". Now we are to run the cmd but have our cwd as "/" which means our new cmd gets modified to challenge/run omitting "/" at the start as its not needed since we are already in the dir "/".
```bash
hacker@paths~implicit-relative-paths-from-:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{4Wj0w3vdLb87kc44ClqQjr-XCfC.dlDN1QDL5EzN0czW}
```
**Flag:** `pwn.college{4Wj0w3vdLb87kc44ClqQjr-XCfC.dlDN1QDL5EzN0czW}`
## New Learning
cd ..  would bring me out to the prev dir where my cwd was located (before cmd execution)
## Reference
