# Challenge Description
If you use Linux (or computers) for any reasonable length of time to do any real work, you will eventually run into some variant of the following situation: you want two programs to access the same data, but the programs expect that data to be in two different locations. Luckily, Linux provides a solution to this quandary: links.

Links come in two flavors: hard and soft (also known as symbolic) links. We'll differentiate the two with an analogy:

1. A hard link is when you address your apartment using multiple addresses that all lead directly to the same place (e.g., Apt 2 vs Unit 2).

2. A soft link is when you move apartments and have the postal service automatically forward your mail from your old place to your new place.
In a filesystem, a file is, conceptually, an address at which the contents of that file live. A hard link is an alternate address that indexes that data --- accesses to the hard link and accesses to the original file are completely identical, in that they immediately yield the necessary data. A soft/symbolic link, instead, contains the original file name. When you access the symbolic link, Linux will realize that it is a symbolic link, read the original file name, and then (typically) automatically access that file. In most cases, both situations result in accessing the original data, but the mechanisms are different.

Hard links sound simpler to most people (case in point, I explained it in one sentence above, versus two for soft links), but they have various downsides and implementation gotchas that make soft/symbolic links, by far, the more popular alternative.

In this challenge, we will learn about symbolic links (also known as symlinks). Symbolic links are created with the ln command with the -s argument, like so:
```bash
hacker@dojo:~$ cat /tmp/myfile
This is my file!
hacker@dojo:~$ ln -s /tmp/myfile /home/hacker/ourfile
hacker@dojo:~$ cat ~/ourfile
This is my file!
hacker@dojo:~$
```
You can see that accessing the symlink results in getting the original file contents! Also, you can see the usage of ln -s. Note that the original file path comes before the link path in the command!

A symlink can be identified as such with a few methods. For example, the file command, which takes a filename and tells you what type of file it is, will recognize symlinks:
```bash
hacker@dojo:~$ file /tmp/myfile
/tmp/myfile: ASCII text
hacker@dojo:~$ file ~/ourfile
/home/hacker/ourfile: symbolic link to /tmp/myfile
hacker@dojo:~$
```
Okay, now you try it! In this level the flag is, as always, in /flag, but /challenge/catflag will instead read out /home/hacker/not-the-flag. Use the symlink, and fool it into giving you the flag!
# Thought Process & Solution
Since our actual flag is in /flag but /challenge/catflag will read the flag from destination /home/hacker/not-the-flag. So, i have to make a symlink connecting /flag and /home/hacker/not-the-flag.

In my command i use '~' as that automatically means I am referring to /home/hacker. So after making the symlink and running /challenge/catflag i got my flag.
```bash
hacker@commands~linking-files:~$ ln -s /flag ~/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{UiX_R-biW2oP6--7rZ1WSslF38H.dlTM1UDL5EzN0czW}
```
**Flag:** `pwn.college{UiX_R-biW2oP6--7rZ1WSslF38H.dlTM1UDL5EzN0czW}`
## New Learning
<img width="1110" height="562" alt="image" src="https://github.com/user-attachments/assets/bff52417-9f52-4ecf-bf09-deff25e4ce20" />

ls -ld = this cmd allows us to see permission bits and type of a file

ln = cmd is used to create hard links to a file

ln -s =  used to create soft links to a file

Hard link? -> its basically alternate address to the same file

Symlink -> its like an intermediary address pointing to our actual address and is relative the dir in which we make it.

Commands for both links take two arguments -
  1. file or filepath of which link is to be generated (actual source or destination file that we want to access)

  2. file or filepath to which we connect and use (our pseudo source basically)

file - tells us type of the file, takes one argument - filename as argument
## Reference
Video tagged in the module - [Symlinks](https://youtu.be/m55AtwjBXpE?list=PL-ymxv0nOtqqRAz1x90vxNbhmSkeYxHVC)
