# Challenge Description
Now, let's put the previous levels together! We put a few happy, but diversely-named files in /challenge/files. Go cd there and, using the globbing you've learned, write a single, short (6 characters or less) glob that (when passed as an argument to /challenge/run) will match the files "challenging", "educational", and "pwning"!
# Thought Process & Solution
Im supposed to glob challenginf, educational and pwning - as a first attempt i decided to glob with a common letter among all three i.e. "n" (on second thoughts thats not really specific after taking a glance at the ls output). This tells me i must use "[]" for globbing argument. So next, i see the first letters of the words - c,e,p respectively meaning it will go in the square brackets. I do that and thats still wrong, I conjectured maybe it needs "*" too to read all the letters of the given words - that also fails after a google search i realise putting "*" in the brackets is then treated literally. After some pondering i realise that square brackets will only look for the files named as  "c" "e" "p" exactly so doing [cep]* would solve my problem of reading letters after it.
```bash
hacker@globbing~mixing-globs:~$ cd /c*/f*
hacker@globbing~mixing-globs:/challenge/files$ ls
amazing      educational  incredible  magical     queenly    uplifting   youthful
beautiful    fantastic    jovial      nice        radiant    victorious  zesty
challenging  great        kind        optimistic  splendid   wonderful
delightful   happy        laughing    pwning      thrilling  xenial
hacker@globbing~mixing-globs:/challenge/files$ /c*/r* *n*
Error: you did not use a square bracket glob...
hacker@globbing~mixing-globs:/challenge/files$ /c*/r* [cep]
Your expansion did not expand to the requested files (challenging, educational, 
pwning). Instead, it expanded to:
[cep]
hacker@globbing~mixing-globs:/challenge/files$ /c*/r* [*c*p]
Your expansion did not expand to the requested files (challenging, educational, 
pwning). Instead, it expanded to:
[*c*p]
hacker@globbing~mixing-globs:/challenge/files$ /c*/r* [cep]*
You got it! Here is your flag!
pwn.college{UW6cB0Vli3jCHNX5H_methJU_pD.dVjM4QDL5EzN0czW}
hacker@globbing~mixing-globs:/challenge/files$ 
```
**Flag:** `pwn.college{UW6cB0Vli3jCHNX5H_methJU_pD.dVjM4QDL5EzN0czW}`
## New Learning
## Reference
