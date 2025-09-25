# Challenge Description
You can specify all sorts of paths as arguments to commands, and we'll practice some more with cat. In this level, I'll put the flag in some crazy directory, and I will not allow you to change directories with cd, so no cat flag for you. You must retrieve the flag by absolute path, wherever it is.
# Thought Process & Solution
we were directly told where the flag is so i catted with the absolute flag.
```bash
You cannot use the 'cd' command in this level, and must retrieve the flag by 
absolute path. Plus, I hid the flag in a different directory! You can find it 
in the file /usr/share/enchant-2/flag. Go cat it out **without** cding into 
that directory!
hacker@commands~more-catting-practice:~$ cat /usr/share/enchant-2/flag
pwn.college{MDGfGbaRPfZ5RZdVVhrefy7JvxQ.dBjM5QDL5EzN0czW}
```
**Flag:** `pwn.college{MDGfGbaRPfZ5RZdVVhrefy7JvxQ.dBjM5QDL5EzN0czW}`
## New Learning
## Reference
