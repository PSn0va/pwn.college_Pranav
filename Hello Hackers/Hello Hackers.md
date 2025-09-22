# 1st Module - Hello Hackers
## Intro to Commands
Today I was working in the terminal and I learnt a bit more about how Linux commands work. I used the whoami command, which shows the current logged in user. When I ran it, it just printed out "hacker", which is the name of the user I'm logged in as.
After that, I learnt about how Linux is case sensitive – which means if you type a command like hello, it has to be exactly like that, and not like HELLO or Hello or anything else. That was a bit confusing at first coz I thought commands might work regardless of letter casing, but I guess that's how Linux works.
I also found out that once you run a command and it finishes, the terminal just shows the prompt again, waiting for the next command. It’s kinda cool to see how the shell responds.
Lastly, I tried running the hello command like the task said, and that gave me the flag, so mission success! 🎉
**flag:** `pwn.college{8cf7DYezGhsAFacVzRTR4inqndG.QX3YjM1wSM2EzNzEzW}`
**commands used**
```

hacker@dojo:~$ whoami
hacker
hacker@dojo:~$

```


## Intro to Arguments
Today I learnt more about how Linux commands can have arguments. At first I thought everything we typed was just one big command, but turns out the first word is the actual command, and whatever you type after that are arguments passed to it. Kinda like parameters I guess.
I saw how echo works — like when I typed echo Hello it just printed Hello back to me. Then I tried echo Hello Hackers! and it just echoed both words like a sentence. So that made it clearer how the shell separates the command from the arguments.
Then the task said to run the hello command with one argument: hackers (all lowercase). I almost typed Hello hackers but then I remembered Linux is picky with cases so I fixed it. I ran:
hello hackers
And it worked! Got the flag after that.
One thing I almost messed up was accidentally using echo again instead of hello. Easy to mix up since we just used echo before. But I caught it after re-reading the instructions more carefuly.
Anyway, now I get how command + arguments work in the shell, which I think will help a lot as I keep learning this stuff.
**flag:** `pwn.college{YQl13Tbxo8qLDrL2cDbMj890N38.QX4YjM1wSM2EzNzEzW}`
**commands used**
```
hacker@dojo:~$ echo Hello Hackers!
Hello Hackers!
hacker@dojo:~$
```



## Command History
Today I found out that the terminal actually keeps a history of the commands I’ve typed, which is super helpful cause retyping stuff all the time is kinda annoying.
I learned that you can just press the up arrow key to scroll back through the commands you've already entered. I didn't know that before, so I was typing stuff manually like a newb 😅.
For this challenge, I didn’t even have to type anything — I just opened the terminal and kept hitting the up arrow, and boom! One of the previous commands had the flag in it. Pretty sneaky but clever lol.
I almost missed it at first because I thought I had to type a command again, but then I remembered the hint said the flag was in the history. So yeah, definitely a cool trick I’ll use more from now on.
Overall, this taught me that bash saves everything I type, which could also be useful for going back and checking what I did wrong or right.
**flag:** `pwn.college{YQl13Tbxo8qLDrL2cDbMj890N38.QX4YjM1wSM2EzNzEzW}`


# Conclusion
After doing these three challenges, I’ve gotten a better understanding of how the Linux terminal actually works. First, I learnt that commands like whoami can give you useful info (in that case, your current user), and I also saw how the shell waits for your next command after each one runs.
Then I figured out how arguments work — where the first word is the command (like echo), and the rest are passed in as input. I messed up a little trying echo instead of hello, but I fixed it. Also learned that case sensitivity really matters in Linux.
Lastly, I learned about the command history, which honestly makes life a lot easier. Instead of retyping, I can just hit the arrow keys and scroll back through whatever I already typed. That’s where I found the flag in the last challenge, hidden in the history — pretty cool.
Overall, I feel like I’m getting the hang of the terminal. These were simple tasks, but they taught me the basics that I’m sure will be useful later on.
