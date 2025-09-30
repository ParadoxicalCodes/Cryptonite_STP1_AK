# Challenge Description
Files (or output lines of commands) aren't always in the order you need them! The sort command helps you organize data. It reads lines from input (or files) and outputs them in sorted order:
```bash
hacker@dojo:~$ cat names.txt
  hack
  the
  planet
  with
  pwn
  college
hacker@dojo:~$ sort names.txt
  college
  hack
  planet
  pwn
  the
  with
hacker@dojo:~$
```
By default, sort orders lines alphabetically. Arguments can change this:

  1. -r: reverse order (Z to A)
  2. -n: numeric sort (for numbers)
  3. -u: unique lines only (remove duplicates)
  4. -R: random order!
In this challenge, there's a file at /challenge/flags.txt containing 100 fake flags, with the real flag mixed among them. When sorted alphabetically, the real flag will be at the end (we made sure of this when generating fake flags). Go get it!
# Thought Process & Solution

```bash

```
**Flag:** `pwn.college{}`
## New Learning
## Reference
