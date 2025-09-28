# Challenge Description
First, let's look at redirecting stdout to files. You can accomplish this with the > character, as so:
```bash
hacker@dojo:~$ echo hi > asdf
```
This will redirect the output of echo hi (which will be hi) to the file asdf. You can then use a program such as cat to output this file:
```bash
hacker@dojo:~$ cat asdf
hi
```
In this challenge, you must use this output redirection to write the word PWN (all uppercase) to the filename COLLEGE (all uppercase).
# Thought Process & Solution
echo PWN would output PWN on terminal but i want it saved to file COLLEGE, so redirecting it with ">" solves our challenge.
```bash
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
pwn.college{IWjA2TnKRCM1liPMnerGxqYhkVo.dRjN1QDL5EzN0czW}
```
**Flag:** `pwn.college{IWjA2TnKRCM1liPMnerGxqYhkVo.dRjN1QDL5EzN0czW}`
## New Learning
## Reference
