# Level 15 → Level 16

## Level Goal

The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

### Commands you may need to solve this level

ssh, telnet, nc, openssl, s_client, nmap

### Helpful Reading Material

[Secure Socket Layer/Transport Layer Security on Wikipedia](http://en.wikipedia.org/wiki/Secure_Socket_Layer)

[OpenSSL Cookbook - Testing with OpenSSL](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)

## Solution

Login in to banditx with the password retrieved from [Level x](../Level%20x%20→%20Level%20y/).

```
ssh banditx@bandit.labs.overthewire.org -p 2220
```

Head over to [Level y](../Level%20y%20→%20Level%20z/).

### Password for bandity