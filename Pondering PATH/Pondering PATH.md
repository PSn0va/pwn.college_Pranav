# 13th Module - Pondering PATH
## The Path Variable
In this challenge the goal was to prevent /challenge/run from finding the rm command so it could not delete /flag. I cleared the PATH used by PATH=" " and then executed /challenge/run, the flag was not removed, and the program returned the flag.

**Flag:** `pwn.college{od5C3hFxlaFBsN1C_WpICGMJCrB.QX2cDM1wSM2EzNzEzW}`

**commands used**
```
PATH=" "
/challenge/run
```

## Setting Path
In this challenge the goal was to make the shell find the win command by adjusting PATH. I set PATH=/challenge/more_commands/ and ran /challenge/run, which invoked win and returned the flag.

**Flag:** `pwn.college{4dheikfLw33E_ViZwCS57g794st.QX1cjM1wSM2EzNzEzW}`

**commands used**
```
PATH=/challenge/more_commands/
/challenge/run
```

## Finding Commands
In this challenge the goal was to locate the win command and read the flag that lives in the same directory. I used which win to discover /challenge/paths/17399/win and then ran cat /challenge/paths/17399/flag to read the flag.

**Flag:** `pwn.college{AFkvLfuNxJvqnOCEag2eeTaKXPd.01NzEzNxwSM2EzNzEzW}`

**commands used**
```
which win
cat /challenge/paths/17399/flag
```

## Adding Commands
In this challenge the goal was to provide a win command so /challenge/run could invoke it. I created an executable win script in /home/hacker/scripts that cats the flag, adjusted PATH to include my scripts and the system directory that contains cat (for example PATH=/home/hacker/scripts:/run/dojo/bin), and then executed /challenge/run. The runner found my win, ran it, and returned the flag.

**Flag:** `pwn.college{cRHeIyTPzF5Lplcx6vbnSCpRFmY.QX2cjM1wSM2EzNzEzW}`

**commands used**
```
which cat
mkdir /home/hacker/scripts
nano /home/hacker/scripts/win
chmod a+x /home/hacker/scripts/win
PATH="/home/hacker/scripts:/run/dojo/bin"
/challenge/run
```

## Hijacking Commands
In this challenge the goal was to prevent /challenge/run from removing /flag by supplying a substitute rm that the runner would find first. I created an executable /home/hacker/scripts/rm, put /home/hacker/scripts at the front of PATH (while keeping the system bin in PATH so cat is still available), and executed /challenge/run the runner invoked my rm and returned the flag.

**Flag:** `pwn.college{octJxkky97CNvtWe9SgOGYLAwT8.QX3cjM1wSM2EzNzEzW}`

**commands used**
```
which cat
nano /home/hacker/scripts/rm
chmod a+x /home/hacker/scripts/rm
PATH="/home/acker/scripts:/run/dojo/bin"
/challenge/bin
```

