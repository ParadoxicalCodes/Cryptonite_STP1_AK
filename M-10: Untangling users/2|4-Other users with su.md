# Challenge Description
With no arguments, su will start a root shell (after authenticating with root's password). However, you can also give a username as an argument to switch to that user instead of root. For example:
```bash
hacker@dojo:~$ su some-user
Password:
some-user@dojo:~$
```
Awesome! In this level, you must switch to the zardus user and then run /challenge/run. Zardus' password is dont-hack-me. Good luck!
# Thought Process & Solution

```bash
hacker@users~other-users-with-su:~$ su zardus
Password: 
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{I71Hv0KJNPlrUcM5D7xwha2UbDb.dZTN0UDL5EzN0czW}
```
**Flag:** `pwn.college{I71Hv0KJNPlrUcM5D7xwha2UbDb.dZTN0UDL5EzN0czW}`
## New Learning
## Reference
