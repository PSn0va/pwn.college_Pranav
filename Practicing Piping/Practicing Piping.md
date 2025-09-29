# 6th Module - Practicing Piping
## Redirceting Output 
In this challenge the goal was to use shell output redirection to create a file containing a secret. I ran echo PWN > COLLEGE to write PWN into the file COLLEGE, then used cat COLLEGE to verify the contents were PWN, which produced the flag.

**Flag:** `pwn.college{EqRh01KG_dzjcHXC1DuOIbNU02V.QX0YTN0wSM2EzNzEzW}`

**commands used**
```
echo PWN > COLLEGE
```

## Redirecting More Output
In this challenge the goal was to redirect a program’s stdout into a file named myflag so the program would deposit the secret there. I ran /challenge/run > myflag to send stdout into myflag, then used cat myflag to read the file which printed the flag.

**Flag:** `pwn.college{AGfi7rsk-yukXYt-5C8_UfGy13r.QX1YTN0wSM2EzNzEzW}`

**commands used**
```
/challenge/run > myflag
cat myflag
```

## Appending Output
In this challenge the goal was to use append redirection so a program’s two writes would accumulate in the same file. I ran /challenge/run >> /home/hacker/the-flag to open the program’s stdout in append mode, then used cat /home/hacker/the-flag to read the concatenated result. The file contained the flag.

**Flag:** `pwn.college{42DjTLMlJ9Ukh_tXDISVOhaTU8v.QX3ATO0wSM2EzNzEzW}`

**commands used**
```
/challenge/run >> /home/hacker/the-flag
cat /home/hacker/the-flag
```

## Redirecting Errors 
In this challenge the goal was to redirect a program’s stdout into a file named myflag and its stderr into a file named instructions. I ran /challenge/run > myflag 2> instructions to capture output and errors separately, then used cat instructions to read the program's feedback and cat myflag to read the flag.

**Flag:** `pwn.college{oelsKrZt36KZUHjHdp6ITu4znOb.QX3YTN0wSM2EzNzEzW}`

**commands used**
```
/challenge/run > myflag 2> instructions
cat instructions
cat myflag
```

## Redirecting Input
In this challenge the goal was to redirect a program’s stdin from a file named PWN containing the value COLLEGE. I wrote the value into the file with echo COLLEGE > PWN, then ran /challenge/run < PWN so the program read its input from PWN and produced the flag.

**Flag:** `pwn.college{oKc6uBr-rMHbR9alvWz5uuhttCu.QXwcTN0wSM2EzNzEzW}`

**commands used**
```
echo COLLEGE > PWN
/challenge/run < PWN
```

##
