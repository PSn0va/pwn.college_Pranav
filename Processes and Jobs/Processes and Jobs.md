# 9th Module-Processes and Jobs
## Listing Processes
In this challenge the goal was to find a randomized, non-listable /challenge by inspecting running processes so I could run it and get the flag. I ran ps -ef, found the process /challenge/7479-run-11062, executed /challenge/7479-run-11062, and the program printed the flag on the final line.

**Flag:** `pwn.college{8ZBaDKbOTC6JFYtG11nxz7CvsgO.QX4MDO0wSM2EzNzEzW}`

**commands used**
```
ps -ef
/challenge/7479-run-11062
```

## Killing Processes
In this challenge the goal was to stop a blocking process so I could run /challenge/run and obtain the flag. I listed processes with ps -e | grep sleep, found the sleep process with PID 137, issued kill 137 to terminate it, and then executed /challenge/run, the program printed the flag on the final line.

**Flag:** `pwn.college{k2c4YVZdD7nIdAN05SaYwy688vl.QXyQDO0wSM2EzNzEzW}`

**commands used**
```
ps -e | grep sleep
```

## Interrupting Processes
In this challenge the goal was to stop a blocking process so I could run /challenge/run and obtain the flag. I started /challenge/run, sent an interrupt with Ctrl-C (which delivers SIGINT) to terminate it, and the program printed the flag.

**Flag:** `pwn.college{woSaLwPWXV_wzlN-jeJFw45OuUG.QXzQDO0wSM2EzNzEzW}`

**commands used**
```
/challenge/run
^c
```

## Killing Misbehaving Processes
In this challenge the goal was to kill a decoy process that was holding the read end of a FIFO so /challenge/run could write the real flag to /tmp/flag_fifo. I listed processes ps aux, found the decoy process with PID 142, issued kill 142 to terminate it, then ran /challenge/run and read the FIFO with cat /tmp/flag_fifo; the program printed the flag.

**Flag:** `pwn.college{gvBowlcDoVvyDsSDkOlg-WzSz0-.0FNzMDOxwSM2EzNzEzW}`

**commands used**
```
ps aux
kill 142
/challenge/run
cat /tmp/flag_fifo
```

## Suspending Processes
In this challenge the goal was to suspend a running /challenge/run so a second instance could be launched in the same terminal. I started /challenge/run, suspended it with Ctrl‑Z (which stops the process), then launched /challenge/run again; the program detected the suspended copy and printed the flag.

**Flag:** `pwn.college{0-XRvoa3Txh_Yw28BrDZnloJq2H.QX1QDO0wSM2EzNzEzW}`

**commands used**
```
/challennge/run
^z
/challenge/run
```

## Resuming Processes
In this challenge the goal was to suspend a running /challenge/run and then resume it so it would print the flag. I started /challenge/run, suspended it with Ctrl‑Z (stopping the process), then brought it back to the foreground with fg; the program resumed and printed the flag.

**Flag:** `pwn.college{88K286r74SNVGyCt-1tggn4SxGP.QX2QDO0wSM2EzNzEzW}`

**commands used**
```
/challenge/run
^Z
fg
```

## Backgrounding Processes
In this challenge the goal was to have a running (not suspended) copy of /challenge/run in the same terminal so a second invocation would detect it. I started /challenge/run, suspended it with Ctrl‑Z, resumed it in the background with bg, then launched /challenge/run again; the program detected the backgrounded instance and printed the flag.

**Flag:** `pwn.college{YE5FGp2NiMIqUkJ5IyjGnm8EDmJ.QX3QDO0wSM2EzNzEzW}`

**commands used**
```
/challenge/run
^Z
bg
/challenge/run
```

## Foregrounding Processes
In this challenge the goal was to background a running /challenge/run and then bring it back to the foreground. I started /challenge/run, suspended it with Ctrl‑Z, resumed it in the background with bg, then foregrounded it with fg; the program resumed and printed the flag.

**Flag:**pwn.college{YzuBNkuxgpBpkSMwdnm62J2sycD.QX4QDO0wSM2EzNzEzW}

**commands used**
```
/challenge/run
^Z
bg
fg
```

## Starting Backgrounded Processes
In this challenge the goal was to start /challenge/run directly in the background so it could continue running while I used the shell. I launched it with /challenge/run &, the shell reported the job ([1] 142) and returned the prompt, and the program printed the flag.

**Flag:** `pwn.college{soAMvRKoBOy4WHKrxvZMtIOhn9z.QX5QDO0wSM2EzNzEzW}`

**commands used**
```
/challenge/run&
```
## Process Exit Codes
In this challenge the goal was to retrieve the exit code from /challenge/get-code and submit it. I ran /challenge/get-code, checked the exit code with echo $? which returned 84, then executed /challenge/submit-code 84, the program printed the flag.

**Flag:** `pwn.college{oq8XIAYj4wF9MmH7U1yaqOt6AiH.QX5YDO1wSM2EzNzEzW}`

**commands used**
```
/challenge/get-code
echo $?
/challenge/submit-code 84
```
