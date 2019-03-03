# Level 0 → Level 1

## Level Goal

The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

### Commands you may need to solve this level

ls, cd, cat, file, du, find

## Solution

At this point you should have connected to OverTheWire server using `ssh`. If not, please check go to [Level 0](../Level%200/) for logging into the server.

The goal of this level is to get to the **readme** file. For this, we can use `ls` which is a command to list the files present in the working directory.

```
bandit0@bandit:~$ ls
readme
```

We can now see the readme file is present. To view the contents, we use `cat`.

```
bandit0@bandit:~$ cat readme
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```

Head over to [Level 2](../Level%201%20→%20Level%202/).

### Password for bandit1

boJ9jbbUNNfktd78OOpsqOltutMc3MY1