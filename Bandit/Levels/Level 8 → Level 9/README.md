# Level 8 → Level 9

## Level Goal

The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

### Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Helpful Reading Material

[The unix commandline: pipes and redirects](http://www.westwind.com/reference/os-x/commandline/pipes.html)

## Solution

Login in to bandit8 with the password retrieved from [Level 8](../Level%207%20→%20Level%208/).

```
ssh bandit8@bandit.labs.overthewire.org -p 2220
```

Just like the [previous](../Level%207%20→%20Level%208/) level we have a huge `data.txt` file. We need to print the unique lines, for this we will use the `uniq` command with the `-u` option. The `-u` specifies `uniq` to only report the lines that appear once. However, `uniq` expects input to be sorted, for this we can use the `sort` command. `sort` can be used on a file directly or can be used with the pipe symbol `|` with output redirection.

```
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
bandit8@bandit:~$ cat data.txt | sort | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```

Head over to [Level 10](../Level%209%20→%20Level%2010/).

### Password for bandit9

UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR