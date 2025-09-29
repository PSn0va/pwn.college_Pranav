# 6th Module - Practicing Piping
## Redirecting Output 
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

## Grepping Stored Results
In this challenge the goal was to redirect a program’s stdout into /tmp/data.txt and then search that large file for the flag. I ran /challenge/run > /tmp/data.txt to save the output, then used grep pwn /tmp/data.txt to locate the flag.

**Flag:** `pwn.college{QtHAzHECWVxsE1Gjg_1DxHUaxId.QX4EDO0wSM2EzNzEzW}`

**commands used**
```
/challenge/run > /tmp/data.txt
grep pwn /tmp/data.txt
```

##  Grepping Live Output
In this challenge the goal was to pipe a program’s stdout into grep to filter the flag from a large output stream. I ran /challenge/run | grep pwn to connect the program’s output directly into grep, which printed the matching lines including the flag. 

**Flag:** `pwn.college{QUPPjNBo3QiOhU2rYLlZUidEX_k.QX5EDO0wSM2EzNzEzW}`

**commands used**
```
/challenge/run | grep pwn
```

## Grepping Errors
In this challenge the goal was to redirect a program’s stderr into grep so I could search the error stream. I duplicated stderr onto stdout and then piped into grep with /challenge/run 2>&1 | grep pwn, which produced the matching lines including the flag. 

**Flag:** `pwn.college{klW70wt1l1ZpTRxVfWlcQ5VifeI.QX1ATO0wSM2EzNzEzW}`

**commands used**
```
/challenge/run 2>&1 | grep pwn
```

## Filtering with Grep 
In this challenge the goal was to filter out decoy lines containing DECOY and reveal the real flag. I ran /challenge/run | grep -v DECOY to exclude decoys, which printed the flag.

**Flag:** `pwn.college{ET9ITFzbWt3O-Igng5EiC6K2lF1.0FOxEzNxwSM2EzNzEzW}`

**commands used**
```
/challenge/run | grep -v DECOY
```

## Duplicating Piped Data with Tee 
In this challenge the goal was to intercept a program’s output with tee so I could read the secret it produced and pass that secret to the next program. I ran /challenge/pwn | tee /challenge/pwn_output | /challenge/college, inspected /challenge/pwn_output to find the required SECRET_ARG value UrviJBpC, then ran /challenge/pwn --secret UrviJBpC | /challenge/college to receive the flag.

**Flag:** `pwn.college{UrviJBpCagfoFX33DsuKHsYInkV.QXxITO0wSM2EzNzEzW}`

**commands used**
```
/challenge/pwn | tee /challenge/pwn_output | /challenge/college
cat /challenge/pwn_output
/challenge/pwn --secret UrviJBpC | /challenge/college
```

## Process Substitution for Input 
In this challenge the goal was to compare the outputs of two commands using process substitution. I ran diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag) which revealed the added line containing the flag.

**Flag:** `pwn.college{86E4p6Y1C1Zc0pHl82CTHfxdEQC.0lNwMDOxwSM2EzNzEzW}`

**commands used**
```
diff <(/challenge/print_decoys) <(/challenge/print_decoysANd_flag)
```

## Writing to Multiple Programs
In this challenge the goal was to duplicate the output of one command as input to two other commands using output process substitution. I ran /challenge/hack | tee >( /challenge/the ) >( /challenge/planet)

This command piped the output of /challenge/hack into tee, which then duplicated the data to both /challenge/the and /challenge/planet. This setup satisfied the challenge and revealed the flag.

**Flag:** `pwn.college{khHSx7Q5zYuN4wTThBW1yfos8fR.QXwgDN1wSM2EzNzEzW}`

**commands used**
```
/challenge/hack | tee >(/challenge/the) >(/challenge/planet)
```

## Split Piping Stderr and Stdout
In this challenge the goal was to redirect /challenge/hack's stderr into /challenge/the and its stdout into /challenge/planet. I ran /challenge/hack 2> >(/challenge/the) | /challenge/planet which satisfied the redirections and produced the flag.

**Flag:** `pwn.college{4ntJkvgUS4w33HdPJuKvx61_TcU.QXxQDM2wSM2EzNzEzW}`

**commands used**
```
/challenge/hack 2> >(/challenge/the) | /challenge/planet
```

## Named Pipes 
In this challenge the goal was to create a FIFO at /tmp/flag_fifo and redirect /challenge/run’s stdout into it. Normally you’d use two terminals (one to read the FIFO and one to write to it), but I managed it in a single terminal by backgrounding the writer. I created the pipe with mkfifo /tmp/flag_fifo

then ran the writer in the background and read the FIFO in the foreground challenge/run > /tmp/flag_fifo & cat /tmp/flag_fifo. Reading the FIFO produced the flag.

**Flag:** `pwn.college{sLi7B4yClRp18zg6qGiqX58PTv-.01MzMDOxwSM2EzNzEzW}`

**commands used**
```
mkfifo /tmp/flag_fifo
/challenge/run > /tmp/flag_fifo & cat /tmp/flag_fifo
```
