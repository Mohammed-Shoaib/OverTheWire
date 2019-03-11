# Level 9 → Level 10

## Level Goal

The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, beginning with several ‘=’ characters.

### Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Solution

Login in to bandit9 with the password retrieved from [Level 9](../Level%208%20→%20Level%209/).

```
ssh bandit9@bandit.labs.overthewire.org -p 2220
```

Running the `ls` command we see a `data.txt` file. We can try to use `grep` with the pattern `"="`, however, the file is in binary. `grep` command does not work for input that is binary. We can see this from below,

```
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ cat data.txt | grep "="
Binary file (standard input) matches
```

This is where we use the `strings` command in unix. `strings` finds and prints text embedded in binary files. It can be used directly on the file or with the pipe symbol `|` with output redirection.

```
bandit9@bandit:~$ strings data.txt | grep "=="
2========== the
========== password
========== isa
========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
```

Alternatively, we could use `grep` directly with the `-a` option which makes `grep` treat binary files as text files. Having several '=' characters for our pattern we get,

```
bandit9@bandit:~$ cat data.txt | grep -a "=========="
```

We can see the password at the end of output,

```
z"========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
bandit9@bandit:~$
```

Head over to [Level 11](../Level%2010%20→%20Level%2011/).

### Password for bandit10

truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk