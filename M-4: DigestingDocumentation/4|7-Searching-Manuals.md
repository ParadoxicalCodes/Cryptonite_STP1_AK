# Challenge Description
You can scroll man pages with the arrow keys (and PgUp/PgDn) and search with /. After searching, you can hit n to go to the next result and N to go to the previous result. Instead of /, you can use ? to search backwards!

Find the option that will give you the flag by reading the challenge man page.
# Thought Process & Solution
This time we are supposed to find the correct argument in the man page, after opening the man page i see a lot of arguments so i press "/" and search with flag as my filter. 

<img width="1103" height="747" alt="image" src="https://github.com/user-attachments/assets/bb7e6f54-df1c-4a39-a113-1ce7009d0b1d" />

And after going forward with the results by pressing "n" i see a possible argument that gives me the flag. Running that gives me the flag.
```bash
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --yxmbz
Initializing...
Correct usage! Your flag: pwn.college{0KTBPXDWA9P-FMVOCNKvH_qDGTy.dVTM4QDL5EzN0czW}
```
**Flag:** `pwn.college{0KTBPXDWA9P-FMVOCNKvH_qDGTy.dVTM4QDL5EzN0czW}`
## New Learning
## Reference
