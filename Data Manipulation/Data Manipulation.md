# 8th Module - Data Manipulation
## Translating Characters
In this challenge the goal was to undo a case-swapping transformation using the tr command. The program at /challenge/run printed the flag, but with all letter casing reversed — lowercase letters became uppercase, and uppercase became lowercase. To fix this, I used the command /challenge/run | tr 'A-Za-z' 'a-zA-Z', which swaps the case of all letters back to their original form. As I pressed enter, it provided me with the correct flag.

**Flag:** `pwn.college{QyKfS2pY5qSBeFhT8vsowhgP2ZQ.01MxEzNxwSM2EzNzEzW}`

**commands used**
```
/challenge/run
/challenge/run | tr 'A-Za-z' 'a-zA-z'
```

## Deleting Characters
In this challenge the goal was to remove decoy characters ^ and % that were intermixed among the flag characters using tr -d. I entered the command /challenge/run | tr -d '^%'. As I pressed enter, it provided me with the clean flag.

**Flag:** `pwn.college{YEpuPTYt1wA9Bgo1DjYY7K0SlUD.0FNxEzNxwSM2EzNzEzW}`

**commands used**
```
/challenge/run | tr -d '^%'
```

## Deleting Newlines 
In this challenge the goal was to remove injected newlines from the flag so it becomes a single line. I ran the command /challenge/run | tr -d '\n' which uses tr with -d and the escaped newline \n to delete all newline characters from the program output. As I pressed enter, it printed the reconstructed flag.

**Flag:** `pwn.college{cw-qNaOoCUNK03EiEaKYe6JX8yG.0VNxEzNxwSM2EzNzEzW}`

**commands used**
```
/challenge/run | tr -d '\n'
```

## Extracting the First Lines with Head
In this challenge the goal was to capture just the first seven lines of a verbose program and pass them to another program. I piped the output of /challenge/pwn through head -n 7 and then piped that into /challenge/college like this /challenge/pwn | head -n 7 | /challenge/college. As I pressed enter, it accepted the codes and printed the flag.

**Flag:** `pwn.college{cm8i9IVxWtoG4lYOGuigVFHxxnV.0lNxEzNxwSM2EzNzEzW}`

**commands used**
```
/challenge/pwn | head -n 7 | /challenge/college
```

## Extracting Specific Sections of Text
In this challenge the goal was to extract the second column (which contained the flag characters) from a stream of space-separated lines, then join those characters into a single line. I ran the command /challenge/run | cut -d " " -f 2 | tr -d '\n'. As I pressed enter, it printed the assembled flag.

**Flag:** `pwn.college{UzQ5hOBziELVWFXr--zC6FNI-EZ.01NxEzNxwSM2EzNzEzW}`

**commands used** 
```
/challenge/run
/challenge/run | cut -d " " -f 2 | tr -d '\n'
```

## Sorting Data
In this challenge the goal was to sort a file of 100 fake flags so the real flag — which was generated to sort last alphabetically — would appear at the end. I ran sort /challenge/flags.txt. As I pressed enter, the sorted output placed the real flag on the final line.

**Flag:** `pwn.college{4h-LZcp539aZ3YgB1fZuJCGDbar.0FM0MDOxwSM2EzNzEzW}`

**commands used**
```
sort /challenge/flags.txt
```
