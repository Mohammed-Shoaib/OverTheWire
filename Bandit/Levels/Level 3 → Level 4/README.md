# Level 3 → Level 4

## Level Goal

The password for the next level is stored in a hidden file in the **inhere** directory.

### Commands you may need to solve this level

ls, cd, cat, file, du, find

## Solution

Login in to bandit3 with the password retrieved from [Level 3](../Level%202%20→%20Level%203/).

```
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

There is a directory named `inhere`, if we `cd` into the directory and run `ls`,

```
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$
```

We see nothing. This is because the file we are looking for is hidden. To list hidden files, we use `ls` with the `-a` option.

```
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
```

Now we see a file called `.hidden`. The filename starts with `.` because in unix that's how hidden files are denoted. Run `cat` and we get our password.

```
bandit3@bandit:~/inhere$ cat .hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```


Head over to [Level 5](../Level%204%20→%20Level%205/).

### Password for bandit4

pIwrPrtPN36QITSp3EQaw936yaFoFgAB