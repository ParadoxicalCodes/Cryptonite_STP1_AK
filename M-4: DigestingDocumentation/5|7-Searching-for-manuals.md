# Challenge Description
This level is tricky: it hides the manpage for the challenge by randomizing its name. Luckily, all of the manpages are gathered in a searchable database, so you'll be able to search the man page database to find the hidden challenge man page! To figure out how to search for the right manpage, read the man page manpage by doing: man man!

HINT 1: man man teaches you advanced usage of the man command itself, and you must use this knowledge to figure out how to search for the hidden manpage that will tell you how to use /challenge/challenge

HINT 2: though the manpage is randomly named, you still actually use /challenge/challenge to get the flag!
# Thought Process & Solution
This time man challenge as its scrambled - so i start with man man to see if there any useful arguments to find my actual manpage, and going through all arguments only "-k filename" stands out as it searches any match with the filename among all man pages and gives - short descriptions and manual page names with the keyword, as regular expression.

So i did man -k challenge which does result in something and for some reason i mistook it for the actual argument for /challenge/challenge, after rereading about -k i realised jcbtizpdzc is the scrambled name for challenge. So man jcbtizpdzc returns my man challenge page and from there i see my required argument for the flag.

<img width="1091" height="739" alt="image" src="https://github.com/user-attachments/assets/e15ac611-f144-4a4c-90e2-4ca3fb17aaa6" />


```bash
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k challenge
jcbtizpdzc (1)       - print the flag!
hacker@man~searching-for-manuals:~$ /challenge/challenge jcbtizpdzc
Incorrect usage! Please read the hidden challenge man page!
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man jcbtizpdzc
hacker@man~searching-for-manuals:~$ /challenge/challenge --jcbtiz 004
Correct usage! Your flag: pwn.college{Ij_cD0QbS0QAtIi4zPHR0Mp_ZWQ.dZTM4QDL5EzN0czW}
```
**Flag:** `pwn.college{Ij_cD0QbS0QAtIi4zPHR0Mp_ZWQ.dZTM4QDL5EzN0czW}`
## New Learning
## Reference
