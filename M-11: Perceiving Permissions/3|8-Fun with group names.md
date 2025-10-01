# Challenge Description
In the previous levels, you may have noticed that your hacker user is a member of the hacker group, and that zardus is a member of the zardus group. There is a convention in Linux that every user has their own group, but this does not have to be the case. For example, many computer labs will put all of their users into a single, shared users group.

The point is, you've used hacker for the group before, but in this level, that is not going to work. I'll still allow you to use chgrp, but I have randomized the name of the group that your user is in. You will need to use the id command to figure that name out, then chgrp to victory!
# Thought Process & Solution

```bash
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp7701) groups=1000(grp7701)
hacker@permissions~fun-with-groups-names:~$ chgrp grp7701 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{orumF4Ww-7DjkN4m7hHv-1BrotA.dJzNyUDL5EzN0czW}
```
**Flag:** `pwn.college{orumF4Ww-7DjkN4m7hHv-1BrotA.dJzNyUDL5EzN0czW}`
## New Learning
## Reference
