# Level 10 → Level 11

## Level Goal

The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

### Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Helpful Reading Material

[Base64 on Wikipedia](http://en.wikipedia.org/wiki/Base64)

## Solution

Login in to bandit10 with the password retrieved from [Level 10](../Level%209%20→%20Level%2010/).

```
ssh bandit10@bandit.labs.overthewire.org -p 2220
```

Running `ls` and `cat`,

```
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIElGdWt3S0dzRlc4TU9xM0lSRnFyeEUxaHhUTkViVVBSCg==
```

We see the text seems gibberish. This is because the text has been encoded in base64. Unix supports a `base64` command that takes as input any text and outputs the data encoded in the format. To decode, `base64` command has a `-d` option.

```
bandit10@bandit:~$ base64 -d data.txt
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
```

Alternatively, we could also use `cat` with the pipe symbol `|`,

```
bandit10@bandit:~$ cat data.txt | base64 -d
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
```

Head over to [Level 12](../Level%2011%20→%20Level%2012/).

### Password for bandit11

IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR