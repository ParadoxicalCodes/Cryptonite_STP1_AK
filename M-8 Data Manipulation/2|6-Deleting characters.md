# Challenge Description
tr can also translate characters to nothing (i.e., delete them). This is done via a -d flag and an argument of what characters to delete:
```bash
hacker@dojo:~$ echo PAWN | tr -d A
PWN
hacker@dojo:~$
```
Pretty simple! Now you give it a try. I'll intersperse some decoy characters (specifically: ^ and %) among the flag characters. Use tr -d to remove them!
# Thought Process & Solution

```bash
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^ %
tr: extra operand ‘%’
Only one string may be given when deleting without squeezing repeats.
Try 'tr --help' for more information.
hacker@data~deleting-characters:~$ /challenge/run
Your character-stuffed flag:
p%w^n^.^c^o^%l^l^e^%g^e%{^%I^R^n^%Z^V^%o^u^V%nh%9%W^%zP^%s^%T%d^%j%G^%6^%pw^%W%u%p^%M^%c^.%Q^%X^%0^%E^%T%M^3^E^D^%L%5%E^z%N%0%c%z^W^}
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^%
Your character-stuffed flag:
pwn.college{IRnZVouVnh9WzPsTdjG6pwWupMc.QX0ETM3EDL5EzN0czW}
```
**Flag:** `pwn.college{IRnZVouVnh9WzPsTdjG6pwWupMc.QX0ETM3EDL5EzN0czW}`
## New Learning
## Reference
