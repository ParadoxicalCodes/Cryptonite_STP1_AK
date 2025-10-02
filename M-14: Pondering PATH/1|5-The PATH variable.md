# Challenge Description
It turns out that the answer to "How does the shell find ls?" is fairly simple. There is a special shell variable, called PATH, that stores a bunch of directory paths in which the shell will search for programs corresponding to commands. If you blank out the variable, things go badly:
```bash
hacker@dojo:~$ ls
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$ PATH=""
hacker@dojo:~$ ls
bash: ls: No such file or directory
hacker@dojo:~$
```
Without a PATH, bash cannot find the ls command.

In this level, you will disrupt the operation of the /challenge/run program. This program will DELETE the flag file using the rm command. However, if it can't find the rm command, the flag will not be deleted, and the challenge will give it to you! Thus, you must make it so that /challenge/run also can't find the rm command!

Keep in mind: /challenge/run will be a child process of your shell, so you must apply the concepts you learned in Shell Variables to mess with its PATH variable! If you don't succeed, and the flag gets deleted, you will need to restart the challenge to try again!
# Thought Process & Solution
~Minor Doubt here -  wouldn't my /challenge/run not run if i do PATH="" ?~

After thinking a bit about this and searching on google i realise that commenting out PATH would mean that it tells the shell to not look for any directories for commands, normally rm would have its directory stored in PATH as a lookup reference for shell to locate whenever we call the command by its name. Commenting it out doesnt mean my files or commands itself delete away, rather the shell wouldnt know what rm is or where it is i will have to give its absolute path to call it. Thats why /challenge/run gets to run because im giving the absolute path for my command here.
```bash
hacker@path~the-path-variable:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=path~the-path-variable
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=4b85aae31c258fc6f72fb65780dd4379333736856df95957c4cf687164ce96ca
HOME=/home/hacker
LANG=C.UTF-8
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.7z=01;31:*.ace=01;31:*.alz=01;31:*.apk=01;31:*.arc=01;31:*.arj=01;31:*.bz=01;31:*.bz2=01;31:*.cab=01;31:*.cpio=01;31:*.crate=01;31:*.deb=01;31:*.drpm=01;31:*.dwm=01;31:*.dz=01;31:*.ear=01;31:*.egg=01;31:*.esd=01;31:*.gz=01;31:*.jar=01;31:*.lha=01;31:*.lrz=01;31:*.lz=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.lzo=01;31:*.pyz=01;31:*.rar=01;31:*.rpm=01;31:*.rz=01;31:*.sar=01;31:*.swm=01;31:*.t7z=01;31:*.tar=01;31:*.taz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tgz=01;31:*.tlz=01;31:*.txz=01;31:*.tz=01;31:*.tzo=01;31:*.tzst=01;31:*.udeb=01;31:*.war=01;31:*.whl=01;31:*.wim=01;31:*.xz=01;31:*.z=01;31:*.zip=01;31:*.zoo=01;31:*.zst=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.jxl=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.crdownload=00;90:*.dpkg-dist=00;90:*.dpkg-new=00;90:*.dpkg-old=00;90:*.dpkg-tmp=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:*.swp=00;90:*.tmp=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:
LESSCLOSE=/usr/bin/lesspipe %s %s
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
LESSOPEN=| /usr/bin/lesspipe %s
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
hacker@path~the-path-variable:~$ env | grep PATH
MANPATH=/run/dojo/share/man:
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
hacker@path~the-path-variable:~$ echo $PATH
/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
rm: line 1: cat: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{0getLdLoW-TrPvrWirw5UAmbZQK.dZzNwUDL5EzN0czW}
```
**Flag:** `pwn.college{0getLdLoW-TrPvrWirw5UAmbZQK.dZzNwUDL5EzN0czW}`
## New Learning
PATH is an environmental variable in Linux and other Unix-like operating systems that tells the shell which directories to search for executable files (i.e., ready-to-run programs) in response to commands issued by a user. It increases both the convenience and the safety of such operating systems and is widely considered to be the single most important environmental variable.

A user's PATH consists of a series of colon-separated absolute paths that are stored in plain text files. Whenever a user types in a command at the command line that is not built into the shell or that does not include its absolute path and then presses the Enter key, the shell searches through those directories, which constitute the user's search path, until it finds an executable file with that name.

The concentrating by default of most executable files in just a few directories rather than spread all over the filesystem and the use of the PATH variable to find them eliminates the need for users to remember which directories they are in and to type their absolute path names. That is, any such program can be run by merely typing its name, such as ls instead of /bin/ls and head instead of /usr/bin/head, regardless of where the user is currently working on the filesystem. This also greatly reduces the possibility of damage to data or even to the system as a whole from the accidental running of a script that has the same name as a standard command.1

A list of all the current environmental variables and their values for the current user, including all the directories in the PATH variable, can be seen by running the env command without any options or arguments (i.e., input data), i.e.,

```env```

As there can be considerable output, it can be convenient to modify this command so that it displays just the PATH environmental variable and its value. This can be accomplished by using a pipe (represented by the vertical bar character) to transfer the output of env to the grep filter and use PATH as an argument to grep, i.e.,

```env | grep PATH```

Another way to view the contents of just PATH alone is by using the echo command with $PATH as an argument:

```echo $PATH```

echo repeats on the display screen whatever follows it on the command line. The dollar sign immediately preceding PATH tells echo to repeat the value of the variable PATH rather than its name.
## Reference
[What is PATH?](https://www.linfo.org/path_env_var.html)
