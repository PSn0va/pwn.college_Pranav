# 2nd Module - Pondering Paths
## The Root
Today I was working in the terminal and learned a bit more about how Linux file paths work. There was a program called pwn placed right at the root of the filesystem (/), and the task was just to run it.

At first, I was a bit unsure how to do that, but then I remembered we could run programs by typing their absolute path — so I just typed /pwn, hit enter, and boom — it printed the flag right away!

It was a simple task, but it taught me how important absolute paths are in Linux. I also realized that sometimes the easiest solution is the right one — no need to overthink it. Definitely a good intro to navigating the filesystem and running programs directly.

**flag:** `pwn.college{UexaV2m6HZYuF9IzotkI2Oq52yz.QX4cTO0wSM2EzNzEzW}`

**commands used**
```
/pwn
```

## Program and Absolute Paths
Today I was back in the terminal working through another pwn.college level and learned a bit more about absolute paths. This time the challenge program lived in a challenge folder at the root, so the full path was /challenge/run.

I typed the absolute path, Hit Enter, and it printed the flag — nice and simple. The exercise reinforced that executables can live anywhere and that using the absolute path guarantees you run the exact file you mean. No magic, just typing the right path. Mission accomplished! 🎉

**flag:** `pwn.college{UuQO3QByJyNs4fqBRd2lazRe-pP.QX1QTN0wSM2EzNzEzW}`

**commands used**
```
/challenge/run
```

## Position Thy Self
Today I was working around in the terminal and learned more about how the shell’s current working directory matters. The task wanted me to run /challenge/run, but that program checks where you run it from — it only works if you’re in a specific folder.

So I used cd to move there, Then I ran the program with its absolute path. It printed “Correct!!!” and gave the flag. 

**flag:** `pwn.college{Id02mljbbt8ixxyHUWfYngSo3fx.QX2QTN0wSM2EzNzEzW}`

**commands used**
```
cd /usr/aarch64-linux-gnu/include/gnu
/challenge/run
```

## Position Elsewhere
Today I was working in the terminal and learned a bit more about how your current working directory matters. The challenge wanted me to run /challenge/run, but the program checks where you run it from — so I had to cd into the right folder first.

After switching to /etc and running the absolute path, it printed “Correct!!!” and gave the flag. 

**flag:** `pwn.college{MG9gVQeMuVTncSFz8Vtb0GqOqWu.QX3QTN0wSM2EzNzEzW}`

**commands used**
```
cd /etc
/challenge/run
```

## Position Yet Elsewhere
Today I was back in the terminal and learned another little thing about the shell’s working directory. The challenge wanted /challenge/run to be executed from a specific folder, so I changed into that directory and ran it.

It responded “Correct!!!” and printed the flag. 

**flag:** `pwn.college{kZvUANzVymNkmCPd3t9D96PstAS.QX4QTN0wSM2EzNzEzW}`

**commands used**
```
cd /sys/kernel
/challenge/run
```

## Implicit Relative Paths, from /
Today I was back in the terminal and practiced relative paths. The task wanted /challenge/run to be invoked relatively from the root, so I switched to / and ran the path that starts with c.

It printed “Correct!!!” and gave the flag.

**flag:** `pwn.college{QNSx-l-EnXE6AaHRUde5JmVSD7H.QX5QTN0wSM2EzNzEzW}`

**commands used**
```
cd /
challenge/run
```

## Explicit Relative Paths, from /
Today I was in the terminal again and played with explicit relative paths. The trick here was remembering that . means “this directory,” so instead of typing challenge/run I prefixed it with ./ to be explicit.

It printed “Correct!!!” and gave the flag. 

**flag:** `pwn.college{ouqsjZPi41_YMeGoPhJHaXCPMBi.QXwUTN0wSM2EzNzEzW}`

**commands used**
```
cd /
./challenge/run
```

## Implicit Relative Path
Today I was in the terminal again and learned why you sometimes have to be explicit about running programs in the current folder. I cd into /challenge and tried run — bash couldn't find it. So I used ./run to tell the shell run the file in this directory, hit Enter, and it printed the flag.

**flag:** `pwn.college{0T0RGgQ6mwKLtG4eAtSAtHKv96c.QXxUTN0wSM2EzNzEzW}`

**commands used**
```
cd /challenge
./run
```

## Home Sweet Home
Today I was back in the terminal and did a fun little tilde trick. The level wanted /challenge/run to write the flag to an absolute path inside my home dir, but whatever I typed had to be three characters or less before shell expansion.

The neat trick: ~ expands to /home/hacker but counts as one character in my input.

The shell expanded ~/~ to /home/hacker/~, the program wrote the flag there, and then I read it back.

**flag:** `pwn.college{ELDtx5pTjk_khFHVtEotEiMsSG0.QXzMDO0wSM2EzNzEzW}`

**commands used**
```
/challenge/run ~/~
```
