# Challenge Description
You have written your first shell script, but calling it via bash script.sh is a pain. Why do you need that bash?

When you invoke bash script.sh, you are, of course launching the bash command with the script.sh argument. This tells bash to read its commands from script.sh instead of standard input, and thus your shell script is executed.

It turns out that you can avoid the need to manually invoke bash. If your shell script file is executable (recall File Permissions), you can simply invoke it via its relative or absolute path! For example, if you create script.sh in your home directory and make it executable, you can invoke it via /home/hacker/script.sh or ~/script.sh or (if your working directory is /home/hacker) ./script.sh.

Try that here! Make a shellscript that will invoke /challenge/solve, make it executable, and run it without explicitly invoking bash!
# Thought Process & Solution

```bash
hacker@chaining~executable-shell-scripts:~$ ls
COLLEGE  a.sh            flaggg.txt    myflag        output.txt  pwn_output  tee       x.sh
Desktop  cd              instructions  need.txt      planet      rm          the
PWN      college_output  leap          not-the-flag  pwn         t           the-flag
hacker@chaining~executable-shell-scripts:~$ cat a.sh
/challenge/solve
hacker@chaining~executable-shell-scripts:~$ ls -l a.sh
-rwxrwxrwx 1 hacker hacker 17 Oct 23  2024 a.sh
hacker@chaining~executable-shell-scripts:~$ ./a.sh
Congratulations on your shell script execution! Your flag:
pwn.college{MVJcTZyE3xj3ReF13rMAcjBQfmt.dRzNyUDL5EzN0czW}
```
**Flag:** `pwn.college{MVJcTZyE3xj3ReF13rMAcjBQfmt.dRzNyUDL5EzN0czW}`
## New Learning
## Reference
