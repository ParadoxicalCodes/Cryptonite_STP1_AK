# Challenge Description
We can create files. How about directories? You make directories using the mkdir command. Then you can stick files in there!

Watch:
```bash
hacker@dojo:~$ cd /tmp
hacker@dojo:/tmp$ ls
hacker@dojo:/tmp$ ls
hacker@dojo:/tmp$ mkdir my_directory
hacker@dojo:/tmp$ ls
my_directory
hacker@dojo:/tmp$ cd my_directory
hacker@dojo:/tmp/my_directory$ touch my_file
hacker@dojo:/tmp/my_directory$ ls
my_file
hacker@dojo:/tmp/my_directory$ ls /tmp/my_directory/my_file
/tmp/my_directory/my_file
hacker@dojo:/tmp/my_directory$
```
Now, go forth and create a /tmp/pwn directory and make a college file in it! Then run /challenge/run, which will check your solution and give you the flag!
# Thought Process & Solution
Using mkdir cmd i made my required dir then using touch with absolute path of the file i needed to create, i created the file challenge and cross checked it with ls.
```bash
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ touch /tmp/pwn/college
hacker@commands~making-directories:~$ ls /tmp/pwn
college
hacker@commands~making-directories:~$ /challenge/run
Success! Here is your flag:
pwn.college{0myOvHxXyW3XqLzinsr0PNsDD6B.dFzM4QDL5EzN0czW}
```
**Flag:** `pwn.college{0myOvHxXyW3XqLzinsr0PNsDD6B.dFzM4QDL5EzN0czW}`
## New Learning
## Reference
