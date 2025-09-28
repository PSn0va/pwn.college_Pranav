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

## Helpful Programs
In this challenge the goal was to read the program's built‑in help and use the documented options to reveal the secret. I ran /challenge/challenge --help to view the options, discovered -p/--print-value and -g/--give-the-flag, used /challenge/challenge --print-value to get the secret 467, and then ran /challenge/challenge --give-the-flag 467 to obtain the flag.

**Flag:** `pwn.college{4as-Wqm6kb7UJ2UduAeNsBUEqHi.QX3IDO0wSM2EzNzEzW}`

**commands used**
```
/challenge/challenge --help
/challenge/challenge --p
/challenge/challenge --g 467
```

## Help for Builtins
In this challenge the goal was to read the shell builtin help to find the secret value and pass it to the builtin challenge. I ran help challenge to view the builtin's documentation, discovered the --secret option and that the required value is Eq38gMYz, and then ran challenge --secret Eq38gMYz to obtain the flag.

**Flag:** `pwn.college{Eq38gMYznsShWRRp86hsNUc18D9.QX0ETO0wSM2EzNzEzW}`

**commands used**
```
help challenge
challenge --secret Eq38gMYz
```

