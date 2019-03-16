# Level 11 → Level 12

## Level Goal

The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

### Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Helpful Reading Material

[Rot13 on Wikipedia](http://en.wikipedia.org/wiki/Rot13)

## Solution

Login in to bandit11 with the password retrieved from [Level 11](../Level%2010%20→%20Level%2011/).

```
ssh bandit11@bandit.labs.overthewire.org -p 2220
```

Running `ls` and `cat`,

```
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf 5Gr8L4qetPEsPk8htqjhRK8XSP6x2RHh
```

We know from the description that all lowercase and uppercase letters have been rotated by 13 positions. This type of encoding is also known as **rot13**. Unix does not directly support decoding text which is in rot13 format. So, we will use an [online](https://www.rot13.com/) decoder.

Decoding,

![Rot13](https://i.imgur.com/SrTUsVk.png)

Head over to [Level 12](../Level%2012%20→%20Level%2013/).

### Password for bandit12

5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu