# Challenge Description
One of the purposes of piping data is to modify it. Many Linux commands will help you modify data in really cool ways. One of these is tr, which translates characters it receives over standard input and prints them to standard output.

In its most basic usage, tr translates the character provided in its first argument to the character provided in its second argument:
```bash
hacker@dojo:~$ echo OWN | tr O P
PWN
hacker@dojo:~$
```
It can also handle multiple characters, with the characters in different positions of the first argument replaced with associated characters in the second argument.
```bash
hacker@dojo:~$ echo PWM.COLLAGE | tr MA NE
PWN.COLLEGE
hacker@dojo:~$
```
Now, you try it! In this level, /challenge/run will print the flag but will swap the casing of all characters (e.g., A will become a and vice-versa). Can you undo it with tr and get the flag?
# Thought Process & Solution
## Attempt 1 (fail)
The first two tries i understood the whole question incorrectly -  im supposed to toggling all the cases. So i outputted the inccorect flag with /challenge/run then took note of capitalized letters and reversed them with others. But somehow the flag is wrong?
```bash
hacker@data~translating-characters:~$ /challenge/run | tr ABCDEFGHIJKLMNOPQRSTUVWXYZ abcdefghijklmnopqrstuvwxyz
your case-swapped flag:
pwn.college{817dwiyrevnsctfpa3mvxtcm4nt.qxzetm3edl5ezn0czw}

hacker@data~translating-characters:~$ /challenge/run | tr abcdefghijklmnopqrstuvwxyz ABCDEFGHIJKLMNOPQRSTUVWXYZ
YOUR CASE-SWAPPED FLAG:
PWN.COLLEGE{817DWIYREVNSCTFPA3MVXTCM4NT.QXZETM3EDL5EZN0CZW}

hacker@data~translating-characters:~$ /challenge/run
Your case-swapped flag:
PWN.COLLEGE{817dwiyReVnSCTfpa3mvxtcM4nt.qxZetm3edl5eZn0CZw}

hacker@data~translating-characters:~$ /challenge/run | tr abCdEfGhijkLMNOPqRSTuVWxyZ ABcDeFgHIJKlmnopQrstUvwXYz
YoUr cAse-swAppeD FlAg:
pwn.college{817DwIYrevnsctFpA3mvXtcm4nt.QXzetm3eDl5ezn0czw}
```
## Attempt2

```bash

```
**Flag:** `pwn.college{}`
## New Learning
## Reference
