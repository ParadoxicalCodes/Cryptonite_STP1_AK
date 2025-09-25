# Challenge Description
With your knowledge of cd, ls, and cat, we're ready to play a little game!

We'll start it out in /. Normally:
```bash
hacker@dojo:~$ cd /
hacker@dojo:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  proc  run   srv  tmp  var
boot  dev        flag  lib   lib64  media   opt  root  sbin  sys  usr
```
That's a lot of contents! One day, you will be quite familiar with them, but already, you might recognize the flag file and the challenge directory.

In this challenge, I have hidden the flag! Here, you will use ls and cat to follow my breadcrumbs and find it! Here's how it'll work:

Your first clue is in /. Head on over there.
Look around with ls. There'll be a file named HINT or CLUE or something along those lines!
cat that file to read the clue!
Depending on what the clue says, head on over to the next directory (or don't!).
Follow the clues to the flag!
Good luck!
# Thought Process & Solution
## Attempt 1 (unsuccessful)
each time i shifted to a new dir i made sure to do ls -a incase i dont miss any hints and i kept doing this - following all hints until i came to the trapped clue part. This was slightly confusing, i wasnt allowed to cd into the dir or else the clue is destroyed. I was trying to guess what file could be there in the hinted dir but that led to no results. So i decided to cd into it regardless to know which file is the hint and cat it in the next attempt - although its not the actual intended way i guess. I was supposed to do ls and then set my argument for it as path of my hinted directory which would lead me to see the contents of that dir without actually going into it.
```bash
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls -a
.           DOSSIER  challenge  flag  lib32   media  opt   run   sys  var
..          bin      dev        home  lib64   mnt    proc  sbin  tmp
.dockerenv  boot     etc        lib   libx32  nix    root  srv   usr
hacker@commands~an-epic-filesystem-quest:/$ cat flag
cat: flag: Permission denied
hacker@commands~an-epic-filesystem-quest:/$ cat DOSSIER
Lucky listing!
The next clue is in: /usr/share/vim/vim81/lang/zh_CN.UTF-8/LC_MESSAGES
 
The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/share/vim/vim81/lang/zh_CN.ITF-8/LC_MESSAGES
bash: cd: /usr/share/vim/vim81/lang/zh_CN.ITF-8/LC_MESSAGES: No such file or directory
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/share/vim/vim81/lang/zh_CN.UTF-8/LC_MESSAGES
hacker@commands~an-epic-filesystem-quest:/usr/share/vim/vim81/lang/zh_CN.UTF-8/LC_MESSAGES$ ls -a
.  ..  .NOTE  vim.mo
hacker@commands~an-epic-filesystem-quest:/usr/share/vim/vim81/lang/zh_CN.UTF-8/LC_MESSAGES$ cat .NOTE
Tubular find!
The next clue is in: /opt/linux/linux-5.4/fs/iomap
hacker@commands~an-epic-filesystem-quest:/usr/share/vim/vim81/lang/zh_CN.UTF-8/LC_MESSAGES$ cd /opt/linux/linux-5.4/fs/iomap
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/fs/iomap$ ls -a
.                   .direct-io.o.cmd  NUGGET         built-in.a   seek.c
..                  .fiemap.o.cmd     apply.c        direct-io.c  seek.o
.apply.o.cmd        .seek.o.cmd       apply.o        direct-io.o  swapfile.c
.buffered-io.o.cmd  .swapfile.o.cmd   buffered-io.c  fiemap.c     swapfile.o
.built-in.a.cmd     Makefile          buffered-io.o  fiemap.o
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/fs/iomap$ cat NUGGET
Lucky listing!
The next clue is in: /usr/lib/R/library/methods
 
The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/fs/iomap$ cd /usr/lib/R/library/methods
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ ls -a
.  ..  DESCRIPTION  INDEX  Meta  NAMESPACE  R  TIP  help  html  libs
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ cat DESCRIPTION
Package: methods
Version: 3.6.3
Priority: base
Imports: utils, stats
Title: Formal Methods and Classes
Author: R Core Team
Maintainer: R Core Team <R-core@r-project.org>
Description: Formally defined methods and classes for R objects,
  plus other programming tools, as described in the reference.
References: John M. Chambers (2008) ``Software for Data Analysis:
        Programming with R''; Springer NY.
License: Part of R 3.6.3
Suggests: codetools
NeedsCompilation: yes
Built: R 3.6.3; x86_64-pc-linux-gnu; 2020-03-28 14:50:50 UTC; unix
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ cat INDEX
.BasicFunsList          List of Builtin and Special Functions
Classes                 S4 Class Documentation
Classes_Details         Class Definitions
Documentation           Using and Creating On-line Documentation for
                        Classes and Methods
GenericFunctions        Tools for Managing Generic Functions
Introduction            Basic use of S4 Methods and Classes
LinearMethodsList-class
                        Class "LinearMethodsList"
LocalReferenceClasses   Localized Objects based on Reference Classes
MethodDefinition-class
                        Classes to Represent Method Definitions
MethodWithNext-class    Class MethodWithNext
Methods                 S4 Class Documentation
MethodsList-class       Class MethodsList, Defunct Representation of
                        Methods
Methods_Details         General Information on Methods
Methods_for_Nongenerics
                        Methods for Non-Generic Functions in Other
                        Packages
Methods_for_S3          Methods For S3 and S4 Dispatch
ObjectsWithPackage-class
                        A Vector of Object Names, with associated
                        Package Names
ReferenceClasses        Objects With Fields Treated by Reference
                        (OOP-style)
S3Part                  S4 Classes that Contain S3 Classes
S4groupGeneric          S4 Group Generic Functions
SClassExtension-class   Class to Represent Inheritance (Extension)
                        Relations
as                      Force an Object to Belong to a Class
callGeneric             Call the Current Generic Function from a Method
callNextMethod          Call an Inherited Method
canCoerce               Can an Object be Coerced to a Certain S4 Class?
cbind2                  Combine two Objects by Columns or Rows
character-class         Classes Corresponding to Basic Data Types
className               Class names including the corresponding package
classRepresentation-class
                        Class Objects
classesToAM             Compute an Adjacency Matrix for Superclasses of
                        Class Definitions
dotsMethods             The Use of '...' in Method Signatures
envRefClass-class       Class '"envRefClass"'
environment-class       Class '"environment"'
evalSource              Use Function Definitions from a Source File
                        without Reinstalling a Package
findClass               Find Class Definitions
findMethods             Description of the Methods Defined for a
                        Generic Function
fixPre1.8               Fix Objects Saved from R Versions Previous to
                        1.8
genericFunction-class   Generic Function Objects
getClass                Get Class Definition
getMethod               Get or Test for the Definition of a Method
getPackageName          The Name associated with a Given Package
hasArg                  Look for an Argument in the Call
implicitGeneric         Manage Implicit Versions of Generic Functions
inheritedSlotNames      Names of Slots Inherited From a Super Class
initialize-methods      Methods to Initialize New Objects from a Class
is                      Is an Object from a Class?
isSealedMethod          Check for a Sealed Method or Class
language-class          Classes to Represent Unevaluated Language
                        Objects
makeClassRepresentation
                        Create a Class Definition
method.skeleton         Create a Skeleton File for a New Method
methods-package         Formal Methods and Classes
new                     Generate an Object from a Class
nonStructure-class      A non-structure S4 Class for basic types
promptClass             Generate a Shell for Documentation of a Formal
                        Class
promptMethods           Generate a Shell for Documentation of Formal
                        Methods
removeMethod            Remove a Method
representation          Construct a Representation or a Prototype for a
                        Class Definition
selectSuperClasses      Super Classes (of Specific Kinds) of a Class
setAs                   Methods for Coercing an Object to a Class
setClass                Create a Class Definition
setClassUnion           Classes Defined as the Union of Other Classes
setGeneric              Create a Generic Version of a Function
setGroupGeneric         Create a Group Generic Version of a Function
setIs                   Specify a Superclass Explicitly
setLoadActions          Set Actions For Package Loading
setMethod               Create and Save a Method
setOldClass             Register Old-Style (S3) Classes and Inheritance
show                    Show an Object
showMethods             Show all the methods for the specified
                        function(s) or class
signature-class         Class '"signature"' For Method Definitions
slot                    The Slots in an Object from a Formal Class
structure-class         Classes Corresponding to Basic Structures
testInheritedMethods    Test for and Report about Selection of
                        Inherited Methods
traceable-class         Classes Used Internally to Control Tracing
validObject             Test the Validity of an Object
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ cat TIP
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/arch/um/include
 
Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ grep pwn.college /opt/linux/linux-5,4/arch/um/include
grep: /opt/linux/linux-5,4/arch/um/include: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ cat pwn.college /opt/linux/linux-5,4/arch/um/include
cat: pwn.college: No such file or directory
cat: /opt/linux/linux-5,4/arch/um/include: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ cat /opt/linux/linux-5,4/arch/um/include
cat: /opt/linux/linux-5,4/arch/um/include: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ cd /opt/linux/linux-5,4/arch/um/include
bash: cd: /opt/linux/linux-5,4/arch/um/include: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ grep pwn.college /opt/linux/linux-5.4/arch/um/include
grep: /opt/linux/linux-5.4/arch/um/include: Is a directory
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ cat /opt/linux/linux-5.4/arch/um/include
cat: /opt/linux/linux-5.4/arch/um/include: Is a directory
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ cd /opt/linux/linux-5.4/arch/um/include
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/um/include$ ls -a
.  ..  CUE-TRAPPED  asm  shared
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/arch/um/include$ cat CUE_TRAPPED
cat: CUE_TRAPPED: No such file or directory
```

## Attempt 2
Armed with the fact that my trapped file name is CUE-TRAPPED it became much easier to proceed forward. From there i kept following the hints until i got the flag.
```bash
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
DOSSIER  boot       dev  flag  lib    lib64   media  nix  proc  run   srv  tmp  var
bin      challenge  etc  home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~an-epic-filesystem-quest:/$ cat DOSSIER
Lucky listing!
The next clue is in: /usr/share/vim/vim81/lang/zh_CN.UTF-8/LC_MESSAGES
 
The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ cd usr/share/vim/vim81/lang/zh_CN.UTF-8/LC_MESSAGES
hacker@commands~an-epic-filesystem-quest:/usr/share/vim/vim81/lang/zh_CN.UTF-8/LC_MESSAGES$ ls -a
.  ..  .NOTE  vim.mo
hacker@commands~an-epic-filesystem-quest:/usr/share/vim/vim81/lang/zh_CN.UTF-8/LC_MESSAGES$ cat .NOTE
Tubular find!
The next clue is in: /opt/linux/linux-5.4/fs/iomap
hacker@commands~an-epic-filesystem-quest:/usr/share/vim/vim81/lang/zh_CN.UTF-8/LC_MESSAGES$ cd /opt/linux/linux-5.4/fs/iomap
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/fs/iomap$ ls -a
.                   .direct-io.o.cmd  NUGGET         built-in.a   seek.c
..                  .fiemap.o.cmd     apply.c        direct-io.c  seek.o
.apply.o.cmd        .seek.o.cmd       apply.o        direct-io.o  swapfile.c
.buffered-io.o.cmd  .swapfile.o.cmd   buffered-io.c  fiemap.c     swapfile.o
.built-in.a.cmd     Makefile          buffered-io.o  fiemap.o
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/fs/iomap$ cat NUGGET
Lucky listing!
The next clue is in: /usr/lib/R/library/methods
 
The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/fs/iomap$ cd /usr/lib/R/library/methods
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ ls -a
.  ..  DESCRIPTION  INDEX  Meta  NAMESPACE  R  TIP  help  html  libs
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ cat TIP
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/arch/um/include
 
Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
cat: '/'$'\033''[200~opt/linux/linux-5.4/arch/um/include/CUE-TRAPPED': No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ cat /opt/linux/linux-5.4/arch/um/include/CUE-TRAPPED
Congratulations, you found the clue!
The next clue is in: /usr/lib/debug/.build-id/f8
hacker@commands~an-epic-filesystem-quest:/usr/lib/R/library/methods$ cd /usr/lib/debug/.build-id/f8
hacker@commands~an-epic-filesystem-quest:/usr/lib/debug/.build-id/f8$ ls -a
.       b50982c8545797b6ef8adedf4dee1d7fb7cafe.debug
..      ba085cda09e99ab734ba1c2891a522aa988052.debug
README
hacker@commands~an-epic-filesystem-quest:/usr/lib/debug/.build-id/f8$ cat README
Great sleuthing!
The next clue is in: /usr/share/perl/5.30.0/unicore/lib/NFKDQC
 
The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/debug/.build-id/f8$ cd /usr/share/perl/5.30.0/unicore/lib/NFKDQC
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/unicore/lib/NFKDQC$ ls -a
.  ..  .GIST  N.pl  Y.pl
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/unicore/lib/NFKDQC$ cat .GIST
Yahaha, you found me!
The next clue is in: /opt/linux/linux-5.4/include/config/ip
 
The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.30.0/unicore/lib/NFKDQC$ cd /opt/linux/linux-5.4/include/config/ip
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/ip$ ls -a
.   EVIDENCE  mroute    multicast.h  nf     pnp    route
..  advanced  mroute.h  multiple     pimsm  pnp.h
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/ip$ cat EVIDENCE
Yahaha, you found me!
The next clue is in: /opt/libslub/.git/objects
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/ip$ cd /opt/libslub/.git/objects
hacker@commands~an-epic-filesystem-quest:/opt/libslub/.git/objects$ ls -a
.   06  0d  1c  42  4d  5b  67  75  7c  86  8e  SECRET  aa  ca  da  ef  f3  fb    pack
..  08  12  26  45  50  60  68  77  82  88  8f  a3      b8  d1  e6  f1  f7  fd
03  0b  19  2f  4a  54  61  6b  78  85  89  95  a4      c2  d6  ed  f2  fa  info
hacker@commands~an-epic-filesystem-quest:/opt/libslub/.git/objects$ cat SECRET
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{EEVUQpM6lJhMbkG7y9OQk6KUZCx.dljM4QDL5EzN0czW}
```
**Flag:** `pwn.college{EEVUQpM6lJhMbkG7y9OQk6KUZCx.dljM4QDL5EzN0czW}`
## New Learning
if i want to see files of a file in some dir without going to it, then the cmd for it is --> "ls /path/of/that/dir"
## Reference
