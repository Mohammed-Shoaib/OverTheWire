# Level 7 → Level 8

## Level Goal

The password for the next level is stored in the file **data.txt** next to the word **millionth**

### Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Solution

Login in to bandit7 with the password retrieved from [Level 7](../Level%206%20→%20Level%207/).

```
ssh bandit7@bandit.labs.overthewire.org -p 2220
```

If we run the following,

```
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ cat data.txt
```

We see `data.txt` is a huge text file. We know the password is next to the word **millionth**. This is where we use the unix command `grep`. 

`grep` command searches a file for a pattern and returns all the lines containing that pattern. 

```
grep [pattern] [filename]
```

`grep` can also be used with the pipe symbol `|` which redirects output. The output can be redirected from `cat`. In this case we only need to specify the pattern that `grep` needs to search.

```
cat [filename] | grep [pattern]
```

Running any of these commands with our pattern **millionth**,

```
bandit7@bandit:~$ grep "millionth" data.txt
millionth       cvX2JJa4CFALtqS87jk27qwqGhBM9plV
bandit7@bandit:~$ cat data.txt | grep "millionth"
millionth       cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```

Head over to [Level 9](../Level%208%20→%20Level%209/).

### Password for bandit8

cvX2JJa4CFALtqS87jk27qwqGhBM9plV