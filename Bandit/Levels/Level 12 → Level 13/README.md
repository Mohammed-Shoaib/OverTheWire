# Level 12 → Level 13

## Level Goal

The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

### Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file

### Helpful Reading Material

[Hex dump on Wikipedia](http://en.wikipedia.org/wiki/Hex_dump)

## Solution

Login in to banditx with the password retrieved from [Level x](../Level%20x%20→%20Level%20y/).

```
ssh banditx@bandit.labs.overthewire.org -p 2220
```

Head over to [Level y](../Level%20y%20→%20Level%20z/).

### Password for bandity