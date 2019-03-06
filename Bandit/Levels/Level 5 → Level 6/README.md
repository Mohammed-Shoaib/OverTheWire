# Level 5 → Level 6

## Level Goal

The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

* human-readable
* 1033 bytes in size
* not executable

### Commands you may need to solve this level

ls, cd, cat, file, du, find

## Solution

Login in to bandit5 with the password retrieved from [Level 5](../Level%204%20→%20Level%205/).

```
ssh bandit5@bandit.labs.overthewire.org -p 2220
```

Going into the `inhere` directory we see a bunch of folders.

```
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere02  maybehere04  maybehere06  maybehere08  maybehere10  maybehere12  maybehere14  maybehere16  maybehere18
maybehere01  maybehere03  maybehere05  maybehere07  maybehere09  maybehere11  maybehere13  maybehere15  maybehere17  maybehere19
```

Each folder has contains a bunch of files, for example listing out the files in `maybehere10`,

```
bandit5@bandit:~/inhere$ cd maybehere10
bandit5@bandit:~/inhere/maybehere10$ ls
-file1  -file2  -file3  spaces file1  spaces file2  spaces file3
```

We will again use the `find` command but this time we have additional constraints. We will use the `size` , `executable`, `exec` and `file` commands together. 

```
bandit5@bandit:~/inhere$ find . -size 1033c ! -executable -exec file {} ';'
./maybehere07/.file2: ASCII text, with very long lines
```

Let's break this down.

From the [previous](../Level%204%20→%20Level%205/) level we know how to use `find` command to get human-readable files.

To get files of a specific size we specify `find` with `-size` option with a suffix for the size:

* `b`: for 512-byte blocks (default)
* `c`: for bytes
* `w`: for two-byte words
* `k`: for Kilobytes (1024 bytes)
* `M`: for Megabytes (1024 Kilobytes)
* `G`: for Gigabytes (1024 Megabytes)

To get executable files `find` has a `-executable` option. Since we are looking for non-executable files we can use the operator `!` which will be true if the expression after it is false.

From this we get the hidden file called `.file2` under `maybehere07` directory. Running the `cat` command,

```
bandit5@bandit:~/inhere$ cd maybehere07
bandit5@bandit:~/inhere/maybehere07$ ls -a
.  ..  -file1  .file1  -file2  .file2  -file3  .file3  spaces file1  spaces file2  spaces file3
bandit5@bandit:~/inhere/maybehere07$ cat .file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```

Head over to [Level 7](../Level%206%20→%20Level%207/).

### Password for bandit6

DXjZPULLxYr17uwoI01bNLQbtFemEgo7