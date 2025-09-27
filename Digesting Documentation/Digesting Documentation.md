# Digesting Documentation
## Learning from Documentaion
In this challenge the goal was to read the (pretend) documentation and invoke /challenge/challenge with the correct argument. The documentation explicitly said to pass --giveflag, so I ran /challenge/challenge --giveflag

The program accepted the argument and printed the flag.

**Flag:** `pwn.college{IxLc93yCcdPWIOgAihnocZVjwZB.QX0ITO0wSM2EzNzEzW}`

**commands used** 
```
/challenge/challenge --giveflag
```

## Learning Complex Usage
In this challenge the goal was to read the level documentation and use /challenge/challenge’s --printfile option to print an arbitrary file. The documentation explained that --printfile takes the path to the file to print, so I invoked /challenge/challenge --printfile /flag

The program accepted the argument and printed the flag.

**Flag:** `pwn.college{8Q6rjZcIakgFQU6dGtlwdMjGdBb.QX1ITO0wSM2EzNzEzW}`

**commands used**
```
/challenge/challenge --printfile /flag
```

## Reading Manuals
In this challenge the goal was to read the manpage and use /challenge/challenge’s --cesihi option to obtain the flag. The manpage documented the secret option, so I invoked /challenge/challenge --cesihi 648.

The program accepted the argument and printed the flag.

**Flag:** `pwn.college{cesihiK6D4bkyIAEs8_kX2YOak7.QX0EDO0wSM2EzNzEzW}`

**commands used**
```
man challenge
/challenge/challenge  --cesihi 648
```

## Searching Manuals
In this challenge the goal was to read the manpage and use /challenge/challenge’s --bda option to obtain the flag. I opened the manpage, used / to search and n/N to navigate, found the --bda option, and invoked /challenge/challenge --bda

The program accepted the option and printed the flag.

**Flag:** `pwn.college{UEsn8g5q83u_UQfqhx1e2pSiqsY.QX1EDO0wSM2EzNzEzW}`

**commands used**
```
man challenge
/challenge/challenge --bda
```

## Searching for Manuals
In this challenge the goal was to read the man manual and use the man database search to find a randomly-named manpage that documents a secret option for /challenge/challenge. I used man -k challenge (as taught by man man) to search the manpage database, discovered the entry gtjtbjpxch describing the flag option, and then ran /challenge/challenge --gtjtbj 472.

The program accepted the option and printed the flag.

**Flag:** `pwn.college{YgtjMGEtCFbECjpB4QxRVJcM7Xh.QX2EDO0wSM2EzNzEzW}`

**commands used**
```
man man
man -k challenge
man gtjtbjpxch
/challenge/challenge --gtjtbj 472
```

