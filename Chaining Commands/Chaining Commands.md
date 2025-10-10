# 12th Module - Chaining Commands
## Chaining with Semicolons
In this challenge the goal was to run two programs back-to-back using ;. I executed /challenge/pwn; /challenge/college, which ran them sequentially and produced the flag.

**Flag:** `pwn.college{0YN4l4VQDLaPa14hI-x1m6eBqO_.QX1UDO0wSM2EzNzEzW}`

**commands used**
```
/challenge/pwn; /challenge/college
```

## Building on Success
In this challenge the goal was to run /challenge/second only if /challenge/first-success succeeded by using the && operator. I verified each program’s behavior, then executed /challenge/first-success && /challenge/second because first-success exited with code 0 the second program ran and produced the flag.

**Flag:** `pwn.college{QtFUOpUWNVZbPLDo4av3TBg4ryj.0lM0MDOxwSM2EzNzEzW`

**commands used**
```
/challenge/first-success && /challenge/second
```

## Handling Failures
In this challenge the goal was to run a fallback command if the first one failed. I ran /challenge/first-failure || /challenge/second first-failure exited non‑zero so second executed and produced the flag.

**Flag:** `pwn.college{gA1VFDJnh_eq4B1qyXy_Ovsk0Wu.01M0MDOxwSM2EzNzEzW}`

**commands used**
/challenge/first-failure || /challenge/second

## Your First Shell Script
In this challenge the goal was to run /challenge/pwn then /challenge/college from a shell script. I created x.sh containing /challenge/pwn; /challenge/college and executed it with bash x.sh. The script ran both commands and produced the flag.

**Flag:** `pwn.college{gE0AUp-5rMO8HCFoLvFDMnHTtzv.QXxcDO0wSM2EzNzEzW}`

**commands used** 
```
echo '/challenge/pwn; /challenge/college' > x.sh
```

## Redirecting Script Output
In this challenge the goal was to pipe the combined output of a script into /challenge/solve. I wrote a script x.sh containing /challenge/pwn; /challenge/college, then ran it and piped its stdout into the solver with bash x.sh | /challenge/solve — the solver accepted the input and printed the flag. 

**Flag:** `pwn.college{wJPQrntzyrznJlHZC9A29uOpNyT.QX4ETO0wSM2EzNzEzW}`

**commands used**
```
echo "/challenge/pwn; /challenge/college" > x.sh
bash x.sh | /challenge/solve
```

## Executable Shell Scripts
In this challenge the goal was to run a shell script directly (without invoking bash). I created a script containing /challenge/solve, made it executable , and executed it by path /home/hacker/script.sh. The script ran and printed the flag.

**Flag:** `pwn.college{Uu-Gt_CZCcUU6faXcC15DWfmXCK.QX0cjM1wSM2EzNzEzW}`

**commands used**
```
echo '/challenge/solve' > /home/hacker/script.sh
chmod u=rx,g=rx,o=rx /home/hacker/script.sh
/home/hacker/script.sh
```

## Understanding Shebangs
In this challenge the goal was to create an executable script with a proper shebang that prints hack the planet. I wrote /home/hacker/solve.sh with #!/bin/bash and echo "hack the planet", made it executable (chmod a+x), and ran /challenge/run which verified the script and returned the flag.

**Flag:** `pwn.college{8nGuKgvGmXL8T6JgNL3jGJH9zhH.0VOzMDOxwSM2EzNzEzW}`

**commands used**
```
printf '%s\n' '#!/bin/bash' 'echo "hack the planet"' > /home/hacker/solve.sh
chmod a+x /home/hacker/solve.h
/challenge/run
```

## Scripting with Arguments
In this challenge the goal was to write /home/hacker/solve.sh to accept two arguments and print them in reverse order. I created the script with #!/bin/bash and echo "$2 $1", verified it with /challenge/run, and got the flag.

**Flag:** `pwn.college{wbUEB7F1AItQwAl6xXkNTdmYqJm.0VNzMDOxwSM2EzNzEzW}.`

**commands used**
```
printf '%s\n' '#!/bin/bash' 'echo "$2 $1"' > /home/hacker/solve.sh
/challenge/run
```

## Scripting with Conditionals
In this challenge the goal was to write a script that prints college only when given the argument pwn. I created /home/hacker/solve.sh with a shebang and a conditional.Made it executable and ran /challenge/run to verify. The script behaved as required and returned the flag.

**Flag:** `pwn.college{YKLnv2Xb9qpI2hk86hg47MIympx.0lNzMDOxwSM2EzNzEzW}`

**commands used**
```
printf '%s\n' '#!/bin/bash' 'if [ "$1" = "pwn" ]' 'then' '  echo "college"' 'fi' > /home/hacker/solve.sh
/challenge/run
```

## Scripting with Default Cases
In this challenge the goal was to write a script that prints college when given the argument pwn and nope for anything else. I created /home/hacker/solve.sh with a shebang and an if/else block.I ran /challenge/run to verify and received the flag.

**Flag:** `pwn.college{sv3FRR9HPc2SYFYZQVnMDMho7-N.01NzMDOxwSM2EzNzEzW}`

**commands used**
```
printf '%s\n' '#!/bin/bash' 'if [ "$1" = "pwn" ]' 'then' '  echo "college"' 'else' ' echo "nope"' 'fi' > /home/hacker/solve.sh
/challenge/run
```

## Scripting with Multiple Conditions
n this challenge the goal was to write /home/hacker/solve.sh to check one argument and print the correct response for several cases. I created a script with a shebang and an if / elif / else / fi chain that prints the planet for hack, college for pwn, linux for learn, unknown for anything else. I ran /challenge/run to verify and received the flag.

**Flag:** `pwn.college{gHREIDKb-dOFUnQAqOmSX6HaGcx.0FOzMDOxwSM2EzNzEzW}`

**Commands used**
```
printf '%s\n' '#!/bin/bash' 'if [ "$1" = "hack" ]' 'then' '  echo "the planet"' 'elif [ "$1" = "pwn" ]' 'then' ' echo "college"' 'elif [ "$1" = "learn" ]' 'then' ' echo "linux"' 'else' ' echo "unknown"' 'fi' > /home/hacker/solve.sh
/challenge/run
```

## Reading Shell Scripts
In this challenge the goal was to read /challenge/run to find the hardcoded password and use it to get the flag. I catted /challenge/run, found the password hack the PLANET, ran /challenge/run and entered that phrase. The script printed the flag.

**Flag:** `pwn.college{sf9-g-R1mnFiUJsa-fTmcJaGnAP.0lMwgDOxwSM2EzNzEzW}`

**Commands used**
```
cat /challenge/run
/challenge/run
hack the PLANET
```
