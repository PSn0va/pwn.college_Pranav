# 11th Module - Perceiving Permissions
## Changing File Ownership
In this challenge the goal was to gain read access to /flag. I used ls -l to inspect files and symlinks eg. not-the-flag -> /flag, then ran chown hacker not-the-flag which followed the symlink and changed /flag’s owner to hacker. After that cat /flag revealed the flag.

**Flag:** `pwn.college{klH9xpU8IMtvygxvqlymCtq4Q0V.QXxEjN0wSM2EzNzEzW}`

**commands used**
```
ls -l
chown hacker not-the-flag
cat /flag
```

## Groups and Files
In this challenge the goal was to read /flag by changing its group ownership. I used id to confirm my groups, ls -l /flag to see it was root:root, then ran chgrp hacker /flag to make the flag readable by my group. After that cat /flag revealed the flag.

**Flag:** `pwn.college{kHCnlzD6AhQATfFqagHBEEN4H89.QXxcjM1wSM2EzNzEzW}`

**commands used**
```
id
ls -l /flag
chgrp hacker /flag
cat /flag
```

## Fun with Groups Names
In this challenge the goal was to read /flag by changing its group to my (randomized) user group. I ran id to learn my group name (grp13855), verified the flag was root:root with ls -l /flag, then ran chgrp grp13855 /flag and finally cat /flag to read the flag.

**Flag:** `pwn.college{UnhOfIUCjt42rs4Kx6HP63VuDdj.QXycjM1wSM2EzNzEzW}`

**commands used**
```
id
ls -l
chgrp grp13855 /flag
cat /flag
```

## Changing Permissions
In this challenge the goal was to read /flag by modifying its permissions. I used ls -l /flag to confirm it was -r-------- root root, experimented with chmod (trying go-rwx, u+r etc.), and ultimately made it world-readable with chmod o+r /flag. After that cat /flag revealed the flag.

**Flag:** `pwn.college{szLq1WTpk2xlAkPYcO3eJNl7E9s.QXzcjM1wSM2EzNzEzW}`

**commands used**
```
ls -l /flag
chmod go-rwx /flag
chmod u+r /flag
chmod o+r /flag
ls -l /flag
cat /flag
```

## Executable Files
In this challenge the goal was to make /challenge/run executable so it would print the flag. I used ls -l /challenge/run to confirm it lacked execute bits, then used chmod u+x /challenge/run to add the user execute bit. Running /challenge/run then produced the flag.

**Flag:** `pwn.college{EaWZ-GNf36e0pLHcLB9so1uHTmu.QXyEjN0wSM2EzNzEzW}`

**commands used**
```
ls -l /challenge/run
chmod u+x /challenge/run
/challenge/run
```

## Permission Tweaking Practice
In this challenge the goal was to practice precise chmod tweaks until I earned the right to make /flag readable. I ran /challenge/run, completed eight consecutive rounds by applying the exact permission sets requested, and the challenge then allowed me to change /flag's mode. Finally I ran chmod u+r /flag and cat /flag to read the flag.

**Flag:** `pwn.college{4tcUmTCepYxu35AC-8inTfyzP5g.QXwEjN0wSM2EzNzEzW}`

**commands used**
```
/challenge/run
chmod u=w,g=r,o= /challenge/pwn
chmod u=w,g=,o= /challenge/pwn
chmod u=w,g=,o=x /challenge/pwn
chmod u=w,g=,o= /challenge/pwn
chmod u=rwx,g=,o=rx /challenge/pwn
chmod u=r,g=,o=rx /challenge/pwn
chmod u=r,g=rwx,o=rwx /challenge/pwn
chmod u=rx,g=rwx,o=rwx /challenge/pwn
ls -l /flag
chmod u+r /flag
cat /flag
```

## Permissions Setting Practice
In this challenge the goal was to practice fully setting permission triples (using = and comma‑chaining) until the game let me change /flag. I ran /challenge/run, completed eight rounds by applying the exact permission sets requested, and after the final round I made /flag readable with chmod u+r /flag and cat /flag to obtain the flag.

**Flag:** `pwn.college{U8JSSD11bF_teYgVAqBq4fSaUff.QXzETO0wSM2EzNzEzW}`

**commands used**
```
chmod u=rx,g=wx,o=rx /challenge/pwn
chmod u=rwx,g=wx,o=w /challenge/pwn
chmod u=rwx,g=rwx,o=rw /challenge/pwn
chmod u=,g=x,o= /challenge/pwn
chmod u=rx,g=,o= /challenge/pwn
chmod u=rx,g=rwx,o= /challenge/pwn
chmod u=wx,g=r,o=rw /challenge/pwn
chmod u=,g=rx,o=rx /challenge/pwn
ls -l /flag
chmod u+r /flag
cat /flag
```

## The SUID Bit
In this challenge the goal was to get a root shell by setting the SUID bit on /challenge/getroot. I used chmod u+s /challenge/getroot, confirmed the s in ls -l (-rwSrwxrwx), then executed /challenge/getroot. The program ran as root, gave a root shell, and I read the flag with cat /flag.

**Flag:** `pwn.college{IN9TviYdhdt31EGvnLiCIIgegtH.QXzEjN0wSM2EzNzEzW}`

**commands used**
```
ls -l /challenge/getroot
chmod u=rws,g=rwx,o=rwx /challenge/getroot
/challenge/getroot
cat /flag
```

