# Challenge Description
Sometimes, you want to grab specific columns of data, such as the first column, the third column, or the 42nd column. For this, there's the cut command.

For example, imagine that you have the following data file:
```bash
hacker@dojo:~$ cat scores.txt
hacker 78 99 67
root 92 43 89
hacker@dojo:~$
```
You could use cut to extract specific columns:
```bash
hacker@dojo:~$ cut -d " " -f 1 scores.txt
hacker
root
hacker@dojo:~$ cut -d " " -f 2 scores.txt
78
92
hacker@dojo:~$ cut -d " " -f 3 scores.txt
99
43
hacker@dojo:~$
```
The -d argument specifies the column delimiter (how columns are separated). In this case, it's a space character. Of course, it has to be in quotes here so that the shell knows that the space is an argument rather than a space separating other arguments! The -f argument specifies the field number (which column to extract).

In this challenge, the /challenge/run program will give you a bunch of lines with random numbers and single characters (characters of the flag) as columns. Use cut to extract the flag characters, then pipe them to tr -d "\n" (like the previous level!) to join them together into a single line. Your solution will look something like /challenge/run | cut ??? | tr ???, with the ??? filled out.
# Thought Process & Solution
we need 6th col and there arent any col seperators so my delimited field should be null ("") why am i getting this as output? Is it because it doesnt count the space as a column? because i took it as a column.

So it seems i have to not consider space as a column? and ignore the numbers but why?
```bash
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run
1681 p
9222 w
5596 n
13096 .
2347 c
9980 o
29597 l
31435 l
10329 e
8699 g
9519 e
18429 {
19556 k
31139 A
25710 f
6491 m
10858 C
15618 g
22597 3
12226 X
7755 4
2483 K
1403 i
1353 I
6281 x
28598 T
20727 y
17463 H
2727 l
27922 F
27782 u
2576 m
16054 _
13422 d
25130 t
23050 Z
29336 d
5093 E
15385 N
3825 .
6952 Q
32135 X
26071 3
16552 E
30307 T
31066 M
7866 3
18603 E
25932 D
3568 L
18308 5
25330 E
10527 z
23709 N
26116 0
18432 c
7998 z
12001 W
26699 }
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d "" -f 6 | tr -d "\n"
23572 p9487 w3323 n19235 .30207 c29066 o23579 l5495 l24854 e5934 g29636 e31807 {4170 k3024 A7665 f18694 m13296 C32379 g15836 322555 X22371 410079 K22386 i9834 I4918 x28800 T28933 y9749 H25945 l23527 F15907 u8710 m27730 _15595 d31042 t1550 Z1912 d23800 E10370 N9272 .30896 Q7582 X10091 327872 E29221 T1853 M15850 330025 E15931 D10278 L26279 524669 E12252 z19821 N20977 024185 c28606 z12358 W27524 }
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 | tr -d "\n"
pwn.college{kAfmCg3X4KiIxTyHlFum_dtZdEN.QX3ETM3EDL5EzN0czW}
```
**Flag:** `pwn.college{}`
## New Learning
## Reference
