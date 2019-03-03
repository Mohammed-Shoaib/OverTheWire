# Level 2 → Level 3

## Level Goal

The password for the next level is stored in a file called **spaces in this filename** located in the home directory

### Commands you may need to solve this level

ls, cd, cat, file, du, find

### Helpful Reading Material

[Google Search for “spaces in filename”](https://www.google.com/search?q=spaces+in+filename)

## Solution

Login in to bandit2 with the password retrieved from [Level 2](../Level%201%20→%20Level%202/).

```
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

If we run `ls` to list the files present,

```
bandit2@bandit:~$ ls
spaces in this filename
```

To `cat` a file with spaces in its name,
```
bandit2@bandit:~$ cat "spaces in this filename"
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```

Head over to [Level 4](../Level%203%20→%20Level%204/).

### Password for bandit3

UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK