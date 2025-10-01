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
hacker@data~sorting-data:~$ sort -r /challenge/flags.txt
pwn.college{4t0LzErfKLS73Ijs2Qa-K2NTyF6.QXwQzM4EDL5EzN0czW}
pwn.college{4t0LzErfKLS73Ijs2Qa-K2NTyF6.QXwQzM4EDL5EzN0czW}
pwn.college{4t0LzErfKLS73Ijs2Qa-K2NTyF6.QXwQzM4EDK5EzN0czW}
pwn.college{4t0LzErfKLS73Ijs2Qa-K2NTyF6.QXwPzM4EDL5EzN0czW}
pwn.college{4t0LzErfKLS73Ijs2Qa-K2NTyF6.PXwQzM4EDL5EzN0czW}
pwn.college{4t0LzErfKLS73Ijs2Qa-K2NTyF5.QXwPzL4EDL5EzN0czW}
pwn.college{4t0LzErfKLS73Ijs2Qa-J2NTxF5.QXwQzM4EDL5EzN0czV}
pwn.college{4t0LzErfKLS73Ijr2Qa-K2NTyF6.QXwQzM4EDL5EzN0czW}
pwn.college{4t0LzErfKLS72Hjs2Pa-K2NTyF6.PXvQzM3EDL5EzN0czV}
pwn.college{4t0LzErfKLS63Ijs2Qa-J1NTyF6.QXvQzM4EDL5EzN0czW}
pwn.college{4t0LzErfKKS63Ijs2Pa-K2NTyF6.QXwQzM4EDL5EzN0czW}
pwn.college{4t0LzEreKLS73Ijs2Qa-K2NTxF6.QXwPzM3EDL5EzN0czW}
pwn.college{4t0LzEreKLS63Ijs2Qa-K2NTyE6.QXwQzM4EDL5EzN0czW}
pwn.college{4t0LzEqfKLS73Ijs2Qa-J2NTyF6.QXwQzL4EDL5DzN0czW}
pwn.college{4t0LzDrfKLS73Ijs1Qa-K2NTyE6.QXvQzM4ECL5EzN0czW}
pwn.college{4t0LzDreKLS73Ijs2Qa-K2NTyF6.QXwQzM4EDL5EzN0czW}
pwn.college{4t0KzErfKLS73Ijs2Qa-K2NTyF5.QXwQyM4EDK5DyM0cyW}
pwn.college{4t0KzErfKLS73Ijr1Qa-K2MTxE6.QWwQzM4EDL5EzN0czW}
pwn.college{4t0KzErfKLS73Iis1Qa-J2NTyF6.QXwQzM4EDL5EzM0czW}
pwn.college{4t0KzErfKLS72Ijs2Qa-K2NTyF6.PXwQzM4EDL5EzN0cyW}
pwn.college{4t0KzErfKLR73Ijs1Qa-J2MSyF6.QXwQzM3ECK4DzM0czW}
pwn.college{4t0KzEqfKLS73Iis2Qa-K2NTyF6.QXwQzL4EDL5DzN0czW}
pwn.college{3t0LyErfJLS73Hjs2Qa-K1NTyF6.QXwQzM4EDL5EzN0czW}
pwn.collegd{4t0LzDrfKLS73Ijr2Qa-K1NTyF5.QXwPzM4DCL5EzN0czW}
pwn.collegd{4t0KzDqfKLR73Ijs2Qa-K2MSyE6.QXwQyM4DCL5DzM0bzW}
pwn.collegd{4s0LzErfKLS73Ijs2Qa-K2NTyF6.QXwQzM4EDL5DzN0czW}
pwn.collefe{4t0LzErfKLS73Ijs2Qa-K2NTxF6.PXwQzM4EDL5DzN0czV}
pwn.collefe{4t0LyDrfJLR63Hjs2Qa-J2NSxF6.PWwQzL3ECL5EzN0bzW}
pwn.colldge{4s0LzErfKLS73Iir2Qa-K2NTyF6.PXvQzL4EDL5EzN0czV}
pwn.colldge{4s0LyDqfJKS73Iir1Pa-K2MSxE6.QXwQzM4EDL4DzM0bzW}
pwn.colldfe{4s0LzEqfKLS73Iis2Pa-K2NTyF6.PWwPzM4DDL4EzN0czV}
pwn.colldfd{3t0LzErfKLS73Ijs2Qa-J2NTyF5.QXwQzL4EDL5DzN0cyW}
pwn.colkege{4t0LzErfKLS73Ijs2Qa-K2NTyF6.QXwQzM4EDL5EzN0czW}
pwn.colkege{4t0LzErfKKS73Ijs2Pa-K2MSyF6.PXwQzM4EDL4EzN0czW}
pwn.colkege{4t0LzDrfKLS73Ijs2Qa-K2NTyF6.QXwQyM4EDL4EzN0czW}
pwn.colkege{4t0LzDrfKLR73Iir2Qa-K2MSyF5.QXwQyL4DCL5EyN0cyV}
pwn.colkege{4t0LyErfJLR73Ijr2Qa-K2NTxF6.PXvQyM4EDK4EzM0czW}
pwn.colkege{3t0LzErfKLS73Ijs2Pa-K2NTyF6.QXwQzM4EDL5EyN0czW}
pwn.colkegd{4t0LzErfKKS63Ijs2Qa-K2MTxE5.QXwPzM4EDL5DzM0bzW}
pwn.colkefe{3t0LyDqeKKS73Iir2Qa-J2NTxF6.PXwQyM4EDK5DyN0czW}
pwn.colkdge{4t0LzErfKLS73Ijr2Qa-K2NTyF6.QXwQzL4EDL5EzN0czW}
pwn.coklege{3t0LzEreKLS73Iis2Qa-K2NTyF6.QWwPyM4DDL5EzN0czW}
pwn.coklefe{4t0LzErfKLS73Ijs2Qa-K2NTyF6.QXwQzM4EDL5DzN0czW}
pwn.cokkegd{4t0KzEreKLS73Hjs2Pa-K1MTyF6.PXvQzM4EDL5EyM0cyW}
pwn.cnllege{4t0LzErfJLR73Ijr2Qa-K2NSyE6.QXvPzM4DCL5EzN0cyW}
pwn.cnllegd{4t0KyDqeJLS72Iis2Qa-K2NTyE6.QXwQzM4ECL5DzN0cyW}
pwn.cnllefd{3s0LyDrfKKS63Ijs2Qa-K2NTyE5.QXwQyM4EDL4EzN0czW}
pwn.cnlkdge{4t0KzDqeKLS72Ijs2Pa-K2MTyF6.QXwQyL4ECL5EzM0bzW}
pwn.cnklege{3t0LzErfKKS72Ijr2Qa-J2NSyF6.PWwQyL4DCL5EzM0czW}
pwn.cnklefe{3s0LyEreJLS63His1Qa-K2MSxF5.QXwQyM4ECL5EyN0cyV}
pwn.cnkldgd{4t0KzErfKLR63Hjr2Qa-J2NSyE6.PWwQyM4EDK4EzN0czV}
pwn.bollege{4t0LzErfKLR73Hjs2Qa-K2NSyF6.QXwQzM4EDL5DzN0bzW}
pwn.bollegd{3t0LyDrfJKS72Ijs2Qa-K2NSyE6.QWwPzL3DCL5EzN0cyW}
pwn.bolkdge{3t0LzDqfKLS72Hjs2Qa-J2NSyF5.QXwQyM4ECL5EzN0cyV}
pwn.boklege{4t0LzDrfKLR63Ijs2Qa-K1NTxF5.PXwQzM4EDL5EzN0czW}
pwn.boklege{3s0LzEqeKKS62Hir2Qa-K2MSyF5.QXwPyM4DDL5EzM0byW}
pwn.bnllege{4t0LzDqeJKS63Ijs2Pa-K2MTxF6.QXwPyM4DDL5EyM0czW}
pwn.bnlkegd{4t0LzEreKLS63Hjr1Qa-K2NSxE6.PWvPzL4EDK5EyM0bzV}
pwm.college{4s0LzErfKLR73Ijs2Qa-K1NSxF6.QXwQzM4DDL5DyM0czW}
pwm.colldge{4s0LzErfKLS63Hjs1Qa-J2NTyE5.PXwQzM4ECL4EzN0czW}
pwm.cokkefe{4t0LzErfKLR72Hjr2Pa-K2NTyF6.QWvQzM3EDL5EzN0czV}
pwm.cnklegd{4t0KzDrfKLS72Ijr2Qa-K1NTxF6.QXwQyM3EDK4DzN0cyW}
pvn.college{4t0LzErfKLS73Ijs2Qa-K2NTyF5.QXwQzM4EDL5DzN0czV}
pvn.college{4t0LzErfKLS73Hjs2Qa-K2NSyF5.QXwPzL3ECL5EzN0czW}
pvn.college{4t0LzErfJLR72Ijs2Qa-K2NTyF6.QWvQzM4EDL5EyN0bzV}
pvn.college{4t0LyErfKLS73Ijs2Pa-K1NTyF5.QXwPyM3EDL5EzN0czW}
pvn.colkdgd{4t0LyEqfKLS72Hjs2Qa-K2NTxF6.QXwQyM4DDL5DzN0czW}
pvn.coklege{4t0LzEqfKLR73Iis2Qa-K1NTyF6.QWwPzM4EDL4EzN0czW}
pvn.cnllege{4t0LyErfKLS73Ijs1Pa-K2NTyF6.QXwQzM4EDL5EzN0czW}
pvn.bolkegd{4t0LzErfKLS73Hir2Qa-K1NTyF6.PXwQzM4EDL5EzN0czW}
pvn.bokldge{4s0KzErfJLR62Iis2Qa-J2MSyF5.PXwQzM3EDL5EyN0bzW}
pvn.bnllefe{4t0LzErfKLS73Ijr2Qa-J2NTyF6.QXwQzL4EDL5EyN0czV}
pvm.collefd{4t0LyEqfKLS62Hjs2Pa-K1NTyF6.QXwQyL4EDL5EyN0cyW}
pvm.coklege{4t0KzEqeKLR62Ijs2Qa-J2NTyF5.QXwQzL4EDL5EzN0czW}
pvm.coklefe{3t0KzDrfKKS62Iis1Qa-K1NTxF6.QXwQzM4DDK5EzN0czV}
pvm.cnlldfd{4t0LzErfKLS73Ijs1Qa-K2NSyE6.QXwPzM4DCK5EzM0czV}
pvm.cnkldfd{3s0KzDrfKLR73Hjs2Pa-J2MTyF6.PXvQzM4DCK5EyM0czV}
pvm.bokkege{4t0LyEreKLS72Hjs2Qa-K2NSyF5.QXwPzM4ECL5DzM0bzV}
own.college{4t0LzEqfKLS72Ijr2Qa-K2MTxF6.PXvQzM4EDL4EzN0czV}
own.college{4t0KzEqfKLS63Ijs2Qa-K2NTxF6.QXwQzL4EDL5EzN0czW}
own.college{3t0LzErfKLS72Hjs2Pa-K2MTxF6.QXwQzL4ECL4EzN0czW}
own.collegd{4t0LzErfKLS73Ijs2Qa-K2NSyE6.QXwQzM4EDL5DzN0czV}
own.collefe{3t0KzErfKLS73Ijs1Pa-K2MSxE5.QWwPzM4DDL4EyM0czV}
own.colldfd{4t0LyDqfKLR63Iir2Qa-K2NSyF6.QXwQzL4DDL5DzN0cyW}
own.colkegd{4s0KzEqfKLS73Ijs2Qa-K1NTyF6.PWwQzM4EDL5EzN0czW}
own.colkdgd{3t0LzDqeKLS63Ijr1Qa-J1NTyE5.QWvQzM4EDL5DzN0czW}
own.cnllege{4s0KzEqfKLS73Ijr1Qa-K2MSyF6.QWvQzM4EDL5EyN0czW}
own.cnlldge{4t0LzErfKLS73Iis2Pa-J2NTyF6.QWwQzM4EDL5DzM0czW}
own.bollege{4t0LzErfKLR73Ijs2Qa-J2NTyF6.QXwQzM4DDL5EzN0czV}
own.bollege{4t0KyDqeKLR63Ijs2Qa-K2NTyF5.QXvQyL4EDL5EzN0byW}
own.bolkege{4t0LyEqfJLR62Hjs2Qa-K2NTxE6.QWwQyM4EDK5EzN0czW}
own.bolkegd{3t0LyDreKLS72Ijs1Qa-K2NSyF5.QWwPzM4DDK5EzN0bzW}
own.bnkkdge{4t0KzErfKKS72Hjs2Qa-J2NTxF6.QWwPyM4ECL5EyN0bzW}
owm.cnklege{3t0LyEqfJLR73Hjs2Pa-K1NTyE6.QWwQzM3DDL4EyN0czW}
ovn.colldge{4t0LyErfKLS73Ijs2Pa-K2NTyF6.QXvPzL4DDK5DzM0bzV}
ovn.coklegd{4t0LzDreKKR72Hjs2Pa-K2MSyF6.QXvQzM4DCL5DzN0bzW}
ovn.cnlldge{3t0LzEreKKR73Ijs2Qa-J2NTyF6.PWwQzL3DDL5EyN0czW}
ovn.bokkdge{4s0LzEreJKS72His1Qa-K2NSxE5.PXwQzM4EDL5EzM0bzW}
ovm.coklege{4s0LzErfJLR73Ijr1Qa-K1MSyF5.QXvQyM4EDL5EyN0cyW}
ovm.bokkege{4t0KyErfJLS73Ijs2Qa-K2NTyF6.PXvQzM4DDK5EyM0czV}
ovm.bnllegd{3t0LzEreJKS63Ijs2Qa-K1NSyF6.QXwQzM3EDL5EyM0czV}

```
**Flag:** `pwn.college{4t0LzErfKLS73Ijs2Qa-K2NTyF6.QXwQzM4EDL5EzN0czW}`
## New Learning
## Reference
