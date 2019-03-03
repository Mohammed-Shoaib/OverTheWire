# Level 1 → Level 2

## Level Goal

The password for the next level is stored in a file called **-** located in the home directory

### Commands you may need to solve this level

ls, cd, cat, file, du, find

### Helpful Reading Material

[Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)

[Advanced Bash-scripting Guide - Chapter 3 - Special Characters](http://tldp.org/LDP/abs/html/special-chars.html)

## Solution

Login in to bandit1 with the password retrieved from [Level 1](../Level%200%20→%20Level%201/).

```
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

If we run `ls` to list the files present,

```
bandit1@bandit:~$ ls
-
```

Sure enough, we see the file called `-`. Now you might think if we directly run `cat`, we can see the contents. However, that's not what happens.

```
cat -

```

We see the shell is waiting for a prompt. This is because in `bash`, the symbol `-` (hyphen) refers to `stdin` or standard input. If we try typing something,

```
bandit1@bandit:~$ cat -
hello from bandit1!
hello from bandit1!

bandit1@bandit:~$
```

The input we type goes into `cat` and gets displayed. You can use `CTRL + C` to abort. So how do we avoid this?

We somehow need to tell bash that we are not referring to `-` for input but to the file present. We can do this by,

```
bandit1@bandit:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```

This let's shell know that we are trying to access the file and we get our password.

Head over to [Level 3](../Level%202%20→%20Level%203/).

### Password for bandit2

CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9