# Level 6 → Level 7

## Level Goal

The password for the next level is stored **somewhere on the server** and has all of the following properties:

* owned by user bandit7
* owned by group bandit6
* 33 bytes in size

### Commands you may need to solve this level

ls, cd, cat, file, du, find, grep

## Solution

Login in to banditx with the password retrieved from [Level 6](../Level%205%20→%20Level%206/).

```
ssh bandit6@bandit.labs.overthewire.org -p 2220
```

We will use the `find` command in combination with `-user`, `-group` and `-size` options. But the file may not be present in our current directory, it could be present anywhere on the server. For this, we search all the files present on the server. We do this by using `/` forward-slash which uses the `find` command from the entire server's root directory.

```
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c
find: ‘/run/lvm’: Permission denied
find: ‘/run/screen/S-bandit31’: Permission denied
find: ‘/run/screen/S-bandit30’: Permission denied
```

At this point we see a bunch of "Permission denied" messages. These are error messages and we can get rid of them by using `2>/dev/null`.

* `2> file`: redirects stderror to file
* `/dev/null`: null device that takes any input and discards it.

Running `find` again we get,

```
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
```

We can now use `cat` to display the contents,

```
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```

Head over to [Level 8](../Level%207%20→%20Level%208/).

### Password for bandit7

HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs