# Challenge Description
Now, let's put your knowledge together. You must master the ultimate piping task: redirect stdout to one program and stderr to another.

The challenge here, of course, is that the | operator links the stdout of the left command with the stdin of the right command. Of course, you've used 2>&1 to redirect stderr into stdout and, thus, pipe stderr over, but this then mixes stderr and stdout. How to keep it unmixed?

You will need to combine your knowledge of >(), 2>, and |. How to do it is a task I'll leave to you.

In this challenge, you have:

/challenge/hack: this produces data on stdout and stderr

/challenge/the: you must redirect hack's stderr to this program

/challenge/planet: you must redirect hack's stdout to this program

Go get the flag!
# Thought Process & Solution
## Attempt 1 (fail)

```bash
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | tee >(/challenge/planet) 2>&1>(/challenge/the)
bash: 1/dev/fd/61: ambiguous redirect
Are you sure you're properly redirecting /challenge/hack's standard error into 
'/challenge/the'?
You must redirect my standard error into '/challenge/the'!
Are you sure you're properly redirecting /challenge/hack's standard error into 
'/challenge/the'?
Are you sure you're properly redirecting /challenge/hack's standard output into 
'/challenge/planet'?
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | tee 2>(/challenge/the) >(/challenge/planet)
tee: 2/dev/fd/63: No such file or directory
This secret data must directly make it to /challenge/planet over my stdout. 
Don't try to copy-paste it; it changes too fast.
23002318133658560
You must redirect my standard error into '/challenge/the'!
Are you sure you're properly redirecting /challenge/hack's standard error into 
'/challenge/the'?
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack | tee >(/challenge/planet) 2>(/challenge/the)
tee: 2/dev/fd/62: No such file or directory
This secret data must directly make it to /challenge/planet over my stdout. 
Don't try to copy-paste it; it changes too fast.
5576121242939023844
You must redirect my standard error into '/challenge/the'!
Are you sure you're properly redirecting /challenge/hack's standard error into 
```

## Attempt 2
So i got confused here for hints went back for previous challenges and in there it discussed another method of process of substitution which looked something like this - "some_cmd > >(cmd)" something like this and at first i didnt understand what it was trying so told chatgpt to explain and i understood then what i had to do and what was the mistake i was committing.



```bash
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/hack) | tee >(/challenge/planet)
This secret data must directly make it to /challenge/planet over my stdout. 
Don't try to copy-paste it; it changes too fast.
This secret data must directly make it to /challenge/planet over my stdout. 
Don't try to copy-paste it; it changes too fast.
16945113382008016764
16945113382008016764
You must redirect my standard error into '/challenge/the'!
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/the) | tee >(/challenge/planet)
This secret data must directly make it to /challenge/planet over my stdout. 
Don't try to copy-paste it; it changes too fast.
4462300541407828943
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{8bOSdeOlSX6FCfUMngijXhq8_Vg.dFDNwYDL5EzN0czW}
```
**Flag:** `pwn.college{8bOSdeOlSX6FCfUMngijXhq8_Vg.dFDNwYDL5EzN0czW}`
## New Learning
## Reference
