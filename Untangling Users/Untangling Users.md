# 10th Module - Untangling Users
## Becoming Root with su
In this challenge the goal was to become root using su so I could read the privileged flag. I ran su and supplied the root password hack-the-planet to get a root shell. I listed the directory and inspected files; myflag contained a decoy value, while the real flag was located in the file not-the-flag. I read the correct file with cat not-the-flag, which printed the flag.

**Flag:** `pwn.college{Yx_rFdJZsA6gNas9s3a8hyBr4gJ.QX1UDN1wSM2EzNzEzW}`

**commands used**
```
su
hack-the-planet
cat myflag
cat not-the-flag
```

## Other Users with su
In this challenge the goal was to switch user to zardus with su and run /challenge/run as that user to obtain the flag. I ran su which gave a zardus shell. I then executed /challenge/run; the program printed the flag.

**Flag:** `pwn.college{YgIeVh_Bp-k_JagGHzD0Z4GRYTa.QX2UDN1wSM2EzNzEzW}`

**commands used**
```
su zardus
dont-hack-me
/challenge/run
```

## Cracking Passwords
In this challenge the goal was to crack a leaked /etc/shadow hash to obtain zardus's password and use su to become that user. I ran john /challenge/shadow-leak, which cracked the hash to reveal the password aardvark. I then ran su zardus, supplied aardvark, and executed /challenge/run; the program printed the flag.

**Flag:** `pwn.college{IBrzhBdWqCwHVs_f-CKRRUnjJJ5.QX3UDN1wSM2EzNzEzW}`

**commands used**
```
john /challenge/shadow-leak
su zardus
aardvark
/challenge/run
```

## Using Sudo
In this challenge the goal was to use sudo to read files that require elevated privileges and retrieve the real flag. I listed files with sudo ls, used sudo cat myflag (which contained a decoy), and then used sudo cat not-the-flag to read the actual flag; the program printed the flag.

**Flag:** `pwn.college{ENqDKYrLBRyhG2JQZUmGCKvzGB8.QX4UDN1wSM2EzNzEzW}`

**commands used**
```
sudo ls
sudo cat myflag
sudo cat not-the-flag
```
