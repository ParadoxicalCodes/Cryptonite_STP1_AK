# Challenge Description
One of the most critical Linux commands is cat. cat is most often used for reading out files, like so:
```bash
hacker@dojo:~$ cat /challenge/DESCRIPTION.md
One of the most critical Linux commands is `cat`.
`cat` is most often used for reading out files, like so:
```
cat will concatenate (hence the name) multiple files if provided multiple arguments. For example:
```bash
hacker@dojo:~$ cat myfile
This is my file!
hacker@dojo:~$ cat yourfile
This is your file!
hacker@dojo:~$ cat myfile yourfile
This is my file!
This is your file!
hacker@dojo:~$ cat myfile yourfile myfile
This is my file!
This is your file!
This is my file!
```
Finally, if you give no arguments at all, cat will read from the terminal input and output it. We'll explore that in later challenges...

In this challenge, I will copy the flag to the flag file in your home directory (where your shell starts). Go read it with cat!
# Thought Process & Solution
```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ ls
COLLEGE  a.sh            flag          leap        planet      rm   the
Desktop  cd              flaggg.txt    myflag      pwn         t    the-flag
PWN      college_output  instructions  output.txt  pwn_output  tee  x.sh
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{407nfghFqa9Zs3cALiHHWd2_f5r.dFzN1QDL5EzN0czW}
```
**Flag:** `pwn.college{407nfghFqa9Zs3cALiHHWd2_f5r.dFzN1QDL5EzN0czW}`
## New Learning
## Reference
