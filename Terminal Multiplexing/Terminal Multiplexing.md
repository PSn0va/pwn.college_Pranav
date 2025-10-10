# 13th Module - Terminal Multiplexing
## Launching Screen
In this challenge the goal was to launch screen to trigger the flag. I ran screen, the session terminated and printed the flag.

**Flag:** `pwn.college{I7FOafYbgbES9B2nhiF-ttkbsN0.0VN4IDOxwSM2EzNzEzW}`

**commands used**
```
screen
```

## Detaching and Attaching 
In this challenge the goal was to detach a screen session, trigger the challenge to send the flag into that detached session, and then reattach to read it. I started screen, detached it with Ctrl‑A then d, ran /challenge/run from my normal shell (which delivered the flag into the detached session), and finally reattached with screen -r to see the flag.

**Flag:** `pwn.college{g-9sanRSNzU4WpMUwYSFdrzPnZV.0lN4IDOxwSM2EzNzEzW}`

**commands used**
```
screen
/challenge/run
```

## Finding Sessions
In this challenge the goal was to find which detached screen session held the flag. I listed sessions with screen -ls, attached to each session until I found the one containing the flag, then read it.

**Flag:** `pwn.college{AzoxeeREfglKGr7x9RcUkPBZD2h.01N4IDOxwSM2EzNzEzW}`

**commands used**
```
screen -ls
screen -r 144
screen -r 147
screen -r 150
```

## Switching Windows
In this challenge the goal was to find the flag inside a multi‑window screen session. I attached the session with screen -r, switched to the other window Ctrl‑A then 0 to view its contents, and read the flag.

**Flag:** `pwn.college{4-cueBhalX8TUYNUmrlnSPbH9Ly.0FO4IDOxwSM2EzNzEzW}`

**Commands used** 
```
screen -r
```

## Detachng and Attaching TMUX
In this challenge the goal was to receive the flag inside a detached tmux session. I started tmux, detached it with Ctrl‑B then d, ran /challenge/run (which delivered the flag into the detached session), then reattached with tmux attach to read the flag.

**Flag:** `pwn.college{IrkIjZaqkUKeq9K0G2LSEbTjzH8.0VO4IDOxwSM2EzNzEzW}`

**commands used**
```
tmux
/challenge/run
tmux a
```

## Switching Windows [TMUX]
In this challenge the goal was to retrieve a flag from a tmux session window. I attached the tmux session, switched to the window containing the flag (using the ctrl+B 0), and read the flag.

**Flag:** `pwn.college{MV5NEvINMtQhug4CnjRMHagURZJ.0FM5IDOxwSM2EzNzEzW}`

**commands used** 
```
tmux a
```

