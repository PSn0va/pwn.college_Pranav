# 3rd Module - Comprehending Commands
## Cat not the Pet but the Command
Today I messed around with the cat command. I learned it prints files to the terminal and can concatenate multiple files.

For the challenge the flag was copied to ~/flag, so I ran cat flag. Got the flag.

**Flag:** `pwn.college{A3aLuiQz5rySNfVmL-BaumiWd3D.QXxcTN0wSM2EzNzEzW}`

**commands used**
```
cat flag
```

## Catting Absolute Paths 
I learned you can give cat an absolute path. In the last level I used cat flag from my home directory, but here the file isn’t copied to my home — it’s readable at /flag.I

I used cat /flag and got the flag

**Flag:** `pwn.college{Q0ri1oCNLpz-fhavxhC1fUIozCo.QX5ETO0wSM2EzNzEzW}`

**commands used**
```
cat /flag
```

## More Catting Practice
I practiced using absolute paths with cat because I wasn't allowed to cd into the directory. The flag was placed in a weird location, so I just pointed cat at the absolute path and got the flag.

**Flag:** `pwn.college{MUS2uEeurdyb_Ne5yQDoFpoyPXB.QXwITO0wSM2EzNzEzW}`

**commands used**
```
cat /lib/firefox-addons/distribution/flag
```

## Grepping for a Needle in a Haystack
I learned to use grep to search inside big files. The challenge put 100,000 lines in /challenge/data.txt, so I searched for the flag (which always starts with pwn.college) and got the flag.

**Flag:** `pwn.college{Q7kMZghaRUGde_b6JT_wnPaucTm.QX3EDO0wSM2EzNzEzW}`

**commands used**
```grep pwn.college /challenge/data.txt```

## Comparing Files
I used diff to compare the two files in /challenge — one has 100 fake flags, the other has those plus the real one./challenge$ diff decoys_only.txt decoys_and_real.txt

The diff shows the extra line (the real flag). Flag found — mission complete!

**Flag:** `pwn.college{4akRlprRLdY4cB6VXz8BUjiGmVZ.01MwMDOxwSM2EzNzEzW}`

**commands used**
```
diff decoys_only.txt decoys_and_real.txt 
```

## Listing Files
In this challenge, the goal was to locate a file with a randomized name inside the /challenge directory. Since the exact filename was not provided, I used the ls command to list all items in /challenge. This revealed a file named 32557-renamed-run-29574.

After identifying the file, I opened it to examine its contents. The file contained a message along with the flag.

**Flag:** `pwn.college{EMvJQXYu3Gu7wnAsg9l2UT6sV76.QX4IDO0wSM2EzNzEzW}`

**commands used**
```
ls /challenge
/challenge/32557-renamed-run-29574
```

## Touching Files 
In this challenge, the goal was to create two empty files named /tmp/pwn and /tmp/college so the challenge runner could detect them. I created the files with touch in /tmp and then executed /challenge/run, which returned the flag.

**Flag:** `pwn.college{YoUUrTmd33KEa9vTXmMeSlbvzlw.QXwMDO0wSM2EzNzEzW}`

**commands used**
```
cd /tmp
touch pwn
touch college
/challenge/run
```

## Removing Filles
In this challenge the objective was to remove a file named delete_me from my home directory and then run the verifier. I removed delete_me with rm, and then executed /challenge/check. The checker confirmed the removal and returned the flag.

**Flag:** `pwn.college{o1x1XmnpiUOE5sHCVA9E8IlFm8V.QX2kDM1wSM2EzNzEzW}`

**commands used**
```
rm delete_me 
/challenge/check
```

## Moving Files
In this challenge the goal was to move /flag into /tmp/hack-the-planet. I ran mv flag /tmp/hack-the-planet to relocate the file, then executed /challenge/check, which verified the move and returned the flag.

**Flag:** `pwn.college{sYvtPKCILhr-oebDS3fWOjBwoIX.0VOxEzNxwSM2EzNzEzW}`

**commands used**
```
cd /
mv flag /tmp/hack-the-planet
/challenge/check
```

## Hidden Files
I listed the root directory with ls -a / to reveal hidden files and found .flag-26552806818534. I read it with cat .flag-26552806818534, which printed the flag. The flag text was displayed by that cat command.

**Flag:** `pwn.college{UUVG5gZJE1yEAk2-MdECymLugny.QXwUDO0wSM2EzNzEzW}`

**commands used**
```
cd /
ls -a
cat .flag-26552806818534
```

## An Epic Filesystem Quest
In this challenge the goal was to follow a chain of filesystem clues using only ls, cd, and cat until the hidden flag was found. I started in /, read the initial clue file, and followed each path it provided. At locations marked “delayed” I cd'd into the directory first so the clue became readable; at locations marked “trapped” I read the clue by specifying its absolute path without cd to avoid triggering the trap. I used ls -a where clues indicated the filename was hidden (dot-prefixed). By following the breadcrumbs and respecting the “delayed” and “trapped” instructions, I eventually located a hidden file named .REVELATION and read the flag.

**Flag:** `pwn.college{EKwlaKtQiWV3BfO4aj_i86TMzNF.QX5IDO0wSM2EzNzEzW}`

**commands used**
```
cd /
ls
cat SECRET
cd /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/TeX/WinIE6
cat NUGGET 
ls /usr/lib/python3/dist-packages/binwalk/magic
cat /usr/lib/python3/dist-packages/binwalk/magic/BRIEF-TRAPPED
cd /usr/local/share/jupyter/lab/themes/@jupyterlab/theme-dark-high-contrast-extension
cat WHISPER 
ls /usr/local/lib/python3.8/dist-packages/setuptools/tests
cat /usr/local/lib/python3.8/dist-packages/setuptools/tests/NOTE-TRAPPED
cd /usr/local/lib/python3.8/dist-packages/networkx/algorithms/components/tests
cat DOSSIER 
cd /etc/iproute2
cat .DISPATCH 
cd usr/local/lib/python3.8/dist-packages/jupyter_server/services/sessions/__pycache__
cat MESSAGE
cd /usr/lib/python3/dist-packages/sage/rings/valuation/__pycache__
cat .REVELATION
```

## Making Directories 
In this challenge the goal was to create a specific directory and file and then invoke the challenge checker to reveal the flag. I started in /tmp, used ls to confirm the directory was empty, created the directory with mkdir pwn, and cd'd into it so subsequent actions happened in the right place. I created an empty file named college using touch college and used ls again to verify the file's presence. Finally I ran the checker by specifying its absolute path /challenge/run so it evaluated the /tmp/pwn/college file and returned the flag.

**Flag:** `pwn.college{ISXzgsr12myKKfehnVvj_Ut-Eap.QXxMDO0wSM2EzNzEzW}`

**commands used**
```
cd /tmp
mkdir pwn
cd pwn
touch college
/challenge/run
```

## Finding Files
In this challenge the goal was to locate a hidden file named flag somewhere on the filesystem using only the find command (and then read it with cat). I ran find / -name flag, ignored the many “Permission denied” errors from restricted directories, and inspected the candidate paths that find returned. After scanning the results I used cat on /usr/lib/debug/.build-id/66/flag luckily the first one had the flag itself if it didn't have then I would have to keep trying till i find one which contains flag.

**Flag:** `pwn.college{IMFTgnaHUlphvZ0axdoZeqw4ovz.QXyMDO0wSM2EzNzEzW}`

**commands used**
```
find / -name flag
cat /usr/lib/debug/.build-id/66/flag
```

## Symbolic Links 
This was a video which briefed us on things like type of file, Symbolic Links and Hard links.

We can use -ld with ls to check the data type of different files(- regular, d directory, l sybolic links, p named pipe etc.).

Symbolic/Soft link refers to other file (ln -s file_name refering place).

Hard Link refer the orignal file (it is treated as orignal file itself)(ln without -s arg).

## Linking Files
In this challenge the goal was to trick /challenge/catflag into reading the real /flag by creating a symbolic link at /home/hacker/not-the-flag that points to /flag. I created the symlink with ln -s /flag /home/hacker/not-the-flag , then ran /challenge/catflag. The program followed the symlink and printed the flag.

**Flag:** `pwn.college{U9AzD7NtvRlVRz4HltEeRk--QSg.QX5ETN1wSM2EzNzEzW}`

**commands used**
```
ln -s /flag /home/hacker/not-the-flag
/challenge/catflag
```

