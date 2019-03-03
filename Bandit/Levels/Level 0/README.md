# Level 0

## Level Goal

The goal of this level is for you to log into the game using SSH. The host to which you need to connect is **bandit.labs.overthewire.org**, on port 2220. The username is **bandit0** and the password is **bandit0**. Once logged in, go to the [Level 1](../Level%200%20→%20Level%201/) page to find out how to beat Level 1.

### Commands you may need to solve this level

ssh

### Helpful Reading Material

[Secure Shell (SSH) on Wikipedia](http://en.wikipedia.org/wiki/Secure_Shell)

[How to use SSH on wikiHow](http://www.wikihow.com/Use-SSH)

## Solution

To `ssh` for a hostname with a given port number,

```
ssh [username]@[hostname] -p [port]

```

Where in our case,

* username → bandit0

* hostname → bandit0@bandit.labs.overthewire.org

* port → 2220

* password (On prompt) → bandit0

So, all we need to do is run,

```
ssh bandit0@bandit.labs.overthewire.org -p 2220
This is a OverTheWire game server. More information on http://www.overthewire.org/wargames

bandit0@bandit.labs.overthewire.org's password:
```

And the connection should now be successful.

Head over to [Level 1](../Level%200%20→%20Level%201/).