# 7th Module - Shell Variables
## Printing Variables
In this challenge the goal was to print a shell variable containing a secret. I ran echo $FLAG to expand and print the FLAG variable, then it presented the falg as an output.

**Flag:** `pwn.college{wuGPMLKOf95K5QlHL8cwqoDyrFq.QX3UTN0wSM2EzNzEzW}`

**commands used**
```
echo $FLAG
```

## Setting Variables
In this challenge we were asked to assign variable PWN the value COLLEGE. I ran the command PWN=COLLEGE, as soon as I did that it presented me with the flag.

**Flag:** `pwn.college{YdXg5ItxaekrIs-gj_5G_WBb3Dy.QX5UTN0wSM2EzNzEzW}`

**commands used**
```
PWN=COLLEGE
```

## Multi Word Variables
In this challenge the goal was to assign multiple word value to the variables which was only possible if I take the whole value in "" . So I entered the command PWN="COLLEGE YEAH", as I clicked on enter it provided me with flag.

**Flag:** `pwn.college{EySWUallp-obxyjt8Mx5DkC2XaB.QXwYTN0wSM2EzNzEzW}`

**commands used**
```
PWN="COLLEGE YEAH"
```

## Exporting Variables
In this challenge the goal was to set one variable with export so it gets passed along when running a program, and set another variable without export so it doesn’t get passed. I entered the commands export PWN=COLLEGE and COLLEGE=PWN, then ran /challenge/run "$PWN". As I pressed enter, it provided me with the flag.

**Flag:** `pwn.college{MjweI0_UNMdxmq9AaJ8phaaG_5H.QXyYTN0wSM2EzNzEzW}`

**commands used**
```
export PWN=COLLEGE
COLLEGE=PWN
/challenge/run "$PWN"
```

## Printing Exported Variables
In this challenge the goal was to list exported environment variables and find the FLAG. I ran env, scanned the output, and saw the FLAG entry.

**Flag:** `pwn.college{ghZf36IX6lU1EkrX_FxigKqEyQT.QX4UTN0wSM2EzNzEzW}`

**commands used**
```
env
```

## Storing Command Output
In this challenge the goal was to store the output of a command into a variable using command substitution. So I ran PWN=$(/challenge/run), then echo "$PWN", and as I pressed enter it returned the flag.

**Flag:** `pwn.college{k39_MIa6D1-XKmVtC8nMHEgi4_W.QX1cDN1wSM2EzNzEzW}`

**commands used**
```
PWN=$(/challenge/run)
echo "$PWN"
```

## Reading Input
In this challenge the goal was to read a value from input into a variable using read. So I ran read PWN, typed COLLEGE, and as I pressed enter it provided the flag.

**Flag:** `pwn.college{YldK09-4UVKC-yXx-ShS0jFnZa4.QX4cTN0wSM2EzNzEzW}`

**commands used**
```
read PWN
```

## Reading Files
In this challenge the goal was to read a file directly into a variable using input redirection. I ran read PWN < /challenge/read_me, and when I pressed enter it returned the flag.

**Flag:** `pwn.college{wMkkVNvsHr7rqbBGNTXhuGWC1Gn.QXwIDO0wSM2EzNzEzW}`

**commands used**
```
read PWN < /challenge/read_me
```

