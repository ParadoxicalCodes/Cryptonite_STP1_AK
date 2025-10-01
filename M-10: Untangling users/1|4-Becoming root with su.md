# Challenge Description
It's not just hackers that need to become root. Oftentimes, you, as the owner of your computer, need to use root access to administer it. Becoming root is a fairly common action that Linux users take, and there are two utilities that exist for this purpose: su and sudo.

In this challenge, we will cover the older one, su (the substitute user command). This is not typically used to elevate to root access anymore, but it is an elegant utility from a more civilized time, and we'll cover it first.

su is a setuid binary:
```bash
hacker@dojo:~$ ls -l /usr/bin/su
-rwsr-xr-x 1 root root 232416 Dec 1 11:45 /usr/bin/su
hacker@dojo:~$
```
Because it has the SUID bit set, su runs as root. Running as root, it can start a root shell! Of course, su is discerning: before allowing the user to elevate privileges to root, it checks to make sure that the user knows the root password:
```bash
hacker@dojo:~$ su
Password: 
su: Authentication failure
hacker@dojo:~$
```
This check against the root password is what obsoletes su. Modern systems very rarely have root passwords, and different mechanisms (that we will learn later) are used to grant administrative access.

But THIS challenge (and only this challenge) does have a root password. That password is hack-the-planet, and you must provide it to su to become root! Go do that, and read the flag!
# Thought Process & Solution

```bash
hacker@users~becoming-root-with-su:~$ su
Password: 
root@users~becoming-root-with-su:/home/hacker# ls -a
.              .bashrc  .lesshst  Desktop         flaggg.txt    not-the-flag  rm        x.sh
..             .cache   .local    PWN             instructions  output.txt    t
.ICEauthority  .config  .mozilla  a.sh            leap          planet        tee
.bash_history  .dbus    .profile  cd              myflag        pwn           the
.bash_logout   .john    COLLEGE   college_output  need.txt      pwn_output    the-flag
root@users~becoming-root-with-su:/home/hacker# ls -a /
.   .dockerenv  boot       dev  flag  lib    lib64   media  nix  proc  run   srv  tmp  var
..  bin         challenge  etc  home  lib32  libx32  mnt    opt  root  sbin  sys  usr
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{wBSFX6W5p_XOZoKuUU5cwus-bUB.dVTN0UDL5EzN0czW}
```
**Flag:** `pwn.college{wBSFX6W5p_XOZoKuUU5cwus-bUB.dVTN0UDL5EzN0czW}`
## New Learning
## Reference
