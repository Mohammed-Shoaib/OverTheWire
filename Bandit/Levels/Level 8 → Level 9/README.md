# Level 8 → Level 9

## Level Goal

The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

### Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Helpful Reading Material

[The unix commandline: pipes and redirects](http://www.westwind.com/reference/os-x/commandline/pipes.html)

## Solution

Login in to banditx with the password retrieved from [Level x](../Level%20x%20→%20Level%20y/).

```
ssh banditx@bandit.labs.overthewire.org -p 2220
```

Head over to [Level y](../Level%20y%20→%20Level%20z/).

### Password for bandity