# Challenge Description
Interestingly, ls doesn't list all the files by default. Linux has a convention where files that start with a . don't show up by default in ls and in a few other contexts. To view them with ls, you need to invoke ls with the -a flag, as so:
```bash
hacker@dojo:~$ touch pwn
hacker@dojo:~$ touch .college
hacker@dojo:~$ ls
pwn
hacker@dojo:~$ ls -a
.college	pwn
hacker@dojo:~$
```
Now, it's your turn! Go find the flag, hidden as a dot-prepended file in /.
# Thought Process & Solution
moved to root dir. Did ls -a to see the hidden files (files prepended with '.' are not visible normally with just 'ls'), and we have a possible option for our flag visible. I did /challenge/run just in case for any hints to see if i missed something and it tells us we can directly read the flag file so i catted our file and got the flag.
```bash
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.           .flag-21282266956252  challenge  home   lib64   mnt  proc  sbin  tmp
..          bin                   dev        lib    libx32  nix  root  srv   usr
.dockerenv  boot                  etc        lib32  media   opt  run   sys   var
hacker@commands~hidden-files:/$ /challenge/run
There's no flag here for you! I made the flag readable but hid it as a .-prepended file in the / directory. Go find it!
hacker@commands~hidden-files:/$ cat .flag-21282266956252
pwn.college{YaHm5WqBFOwhDdq9qRetB3MoumV.dBTN4QDL5EzN0czW}
```
**Flag:** `pwn.college{YaHm5WqBFOwhDdq9qRetB3MoumV.dBTN4QDL5EzN0czW}`
## New Learning
ls -a : lists all hidden files i.e. filenames prepended with a '.'
## Reference
