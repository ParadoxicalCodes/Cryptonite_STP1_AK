# Challenge Description
Recall our example from the previous level:
```bash
hacker@dojo:~$ ls /home/hacker/scripts
goodscript	badscript	okayscript
hacker@dojo:~$ PATH=/home/hacker/scripts
hacker@dojo:~$ goodscript
YEAH! This is the best script!
hacker@dojo:~$
```
What we see here, of course, is the hacker making the shell more useful for themselves by bringing their own commands to the party. Over time, you might amass your own elegant tools. Let's start with win!

Previously, the win command that /challenge/run executed was stored in /challenge/more_commands. This time, win does not exist! Recall the final level of Chaining Commands, and make a shell script called win, add its location to the PATH, and enable /challenge/run to find it!

Hint: /challenge/run runs as root and will call win. Thus, win can simply cat the flag file. Again, the win command is the only thing that /challenge/run needs, so you can just overwrite PATH with that one directory. But remember, if you do that, your win command won't be able to find cat.

You have three options to avoid that:

  1. Figure out where the cat program is on the filesystem. It must be in a directory that lives in the PATH variable, so you can print the variable out (refer to Shell Variables to remember how!), and go through the directories in it (recall that the different entries are separated by :), find which one has cat in it, and invoke cat by its absolute path.
  2. Set a PATH that has the old directories plus a new entry for wherever you create win.
  3. Use read (again, refer to Shell Variables) to read /flag. Since read is a builtin functionality of bash, it is unaffected by PATH shenanigans.

Now, go and win!
# Thought Process & Solution

```bash
hacker@path~adding-commands:~$ nano win
hacker@path~adding-commands:~$ ls
COLLEGE  cd              leap          output.txt  rm        the
Desktop  college_output  myflag        planet      solve.sh  the-flag
PWN      flaggg.txt      need.txt      pwn         t         win
a.sh     instructions    not-the-flag  pwn_output  tee       x.sh
hacker@path~adding-commands:~$ ls -l
total 76
-rw-r--r-- 1 hacker hacker   4 Sep 28 12:41 COLLEGE
drwxr-xr-x 1 hacker hacker   0 Oct  3  2024 Desktop
-rw-r--r-- 1 hacker hacker   8 Sep 28 16:18 PWN
-rwxrwxrwx 1 hacker hacker  17 Oct 23  2024 a.sh
-rw-r--r-- 1 hacker hacker   0 Oct 10  2024 cd
-rw-r--r-- 1 root   hacker  77 Oct 10  2024 college_output
-rw-r--r-- 1 root   hacker   0 Oct 10  2024 flaggg.txt
-rw-r--r-- 1 hacker hacker 829 Sep 28 16:14 instructions
drwxr-xr-x 1 hacker hacker  12 Oct 24  2024 leap
-rw-r--r-- 1 hacker hacker  93 Sep 28 16:14 myflag
-rw-r--r-- 1 root   hacker  77 Sep 30 06:01 need.txt
lrwxrwxrwx 1 hacker hacker   5 Sep 25 21:35 not-the-flag -> /flag
-rw-r--r-- 1 root   hacker  77 Oct 10  2024 output.txt
-rw-r--r-- 1 hacker hacker 169 Oct 10  2024 planet
-rw-r--r-- 1 root   hacker  77 Oct 10  2024 pwn
-rw-r--r-- 1 root   hacker  17 Oct 10  2024 pwn_output
-rwxr-xr-x 1 hacker hacker  10 Oct 23  2024 rm
-rwxr-xr-x 1 hacker hacker 171 Oct  2 05:08 solve.sh
-rw-r--r-- 1 root   hacker  58 Sep 23 23:43 t
-rw-r--r-- 1 hacker hacker 169 Oct 10  2024 tee
-rw-r--r-- 1 hacker hacker 169 Oct 10  2024 the
-rw-r--r-- 1 hacker hacker 435 Sep 28 12:54 the-flag
-rw-r--r-- 1 hacker hacker   0 Oct  2 06:47 win
-rw-r--r-- 1 hacker hacker  35 Oct 23  2024 x.sh
hacker@path~adding-commands:~$ chmod u+x win
hacker@path~adding-commands:~$ PATH="/home/hacker:$PATH"
hacker@path~adding-commands:~$ echo $PATH
/home/hacker:/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
hacker@path~adding-commands:~$ cat /challenge/run
#!/opt/pwn.college/bash

echo "Invoking 'win'...."
win

if [ $? -ne 0 ]
then
	/bin/fold -s <<< "It looks like that did not work... Did you set PATH correctly?"
fi
hacker@path~adding-commands:~$ nano win
hacker@path~adding-commands:~$ 
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{EDdWx1sr8X9W-5Bbm3afaf9h0us.dZzNyUDL5EzN0czW}
```
**Flag:** `pwn.college{EDdWx1sr8X9W-5Bbm3afaf9h0us.dZzNyUDL5EzN0czW}`
## New Learning
## Reference
