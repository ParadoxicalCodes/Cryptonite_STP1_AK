# Challenge Description
Sometimes, the files that you might cat out are too big. Luckily, we have the grep command to search for the contents we need! We'll learn it in this challenge.

There are many ways to grep, and we'll learn one way here:
```bash
hacker@dojo:~$ grep SEARCH_STRING /path/to/file
```
Invoked like this, grep will search the file for lines of text containing SEARCH_STRING and print them to the console.

In this challenge, I've put a hundred thousand lines of text into the /challenge/data.txt file. grep it for the flag!

HINT: The flag always starts with the text pwn.college.
# Thought Process & Solution
```bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{oZI22anbi7BzTdN5F_26NSV2t7W.ddTM4QDL5EzN0czW}
```
**Flag:** `pwn.college{}`
## New Learning
Learnt something about a new cmd 'grep' which is like cat cmd but with a filter.
## Reference
