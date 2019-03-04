# Level 4 → Level 5

## Level Goal

The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

### Commands you may need to solve this level

ls, cd, cat, file, du, find

## Solution

Login in to bandit4 with the password retrieved from [Level 4](../Level%203%20→%20Level%204/).

```
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

Going into the `inhere` directory, we see a bunch of files.

```
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
```

From all these files, we need to get the only human-readable file. For this, we will use the `find` with the `exec` and `file` commands in unix.

```
bandit4@bandit:~/inhere$ find . -exec file {} ';'
.: directory
./-file09: data
./-file06: data
./-file01: data
./-file02: data
./-file05: data
./-file03: data
./-file08: data
./-file07: ASCII text
./-file04: data
./-file00: data
```

Let's break this down. `find .` lists all the files present in the current working directory and all its subdirectories. `exec` executes a specific command for each file found, in this case the `file` command. `file` is command that specifies the type of data contained in a file. The string `{}` is replaced by the current filename being processed. It is mandatory to terminate `exec` with either a semicolon `;` or a plus symbol `+`.

As we can see, the only human-readable file i.e. a file that contains text is `-file07`. However, note that the filename starts with `-` and we saw from before, the command line interprets `-` as a parameter to `cat`. So if we do,

```
bandit4@bandit:~/inhere$ cat -file07
cat: invalid option -- 'f'
Try 'cat --help' for more information.
```

We get the above error. We need to let shell know we are trying to access the file and as we saw from [Level 2](../Level%201%20→%20Level%202/) we can do this by,

```
bandit4@bandit:~/inhere$ cat ./-file07
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```

Head over to [Level 6](../Level%205%20→%20Level%206/).

### Password for bandit5

koReBOKuIDDepwhWk7jZC0RTdopnAYKh