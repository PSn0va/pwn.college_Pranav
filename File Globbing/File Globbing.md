# 5th Module - File Globbing
## Matching With *
In this challenge the goal was to use shell globbing ( * ) so the cd argument is at most four characters and land in /challenge. From my home directory I ran cd /ch* (which expands to /challenge), then executed /challenge/run and received the flag.

**Flag:** `pwn.college{sPbfBD9-4vVocV28-A3_8mTQeUx.QXxIDO0wSM2EzNzEzW}`

**commands used**
```
cd /ch*
/challenge/run
```

## Matching with ?
In this challenge the goal was to use the single‑character glob ? so the cd argument matches /challenge. From my home directory I ran cd /?ha??enge (which expands to /challenge), then executed /challenge/run to obtain the flag.

**Flag:** `pwn.college{g7ARHuT74B9qowa_-Y3OSG2BgKz.QXyIDO0wSM2EzNzEzW}`

**commands used**
```
cd /?ha??enge
/challenge/run
```

## Matching with []
In this challenge the goal was to use the bracket glob [] so the argument to /challenge/run matches file_b, file_a, file_s, and file_h. From my home directory I ran cd /challenge/files, then executed /challenge/run file_[bash] (which expands to file_b file_a file_s file_h) to obtain the flag.

**Flag:** `pwn.college{kydjhRmoAwuMmpimxVsjYGAlSL2.QXzIDO0wSM2EzNzEzW}`

**commands used**
```
cd /challenge/files
/challenge/run file_[bash]
```

## Matching Paths with []
In this challenge the goal was to use the bracket glob [] to match absolute paths for files in /challenge/files. From my home directory I ran /challenge/run /challenge/files/file_[bash] (which expands to /challenge/files/file_b /challenge/files/file_a /challenge/files/file_s /challenge/files/file_h) and obtained the flag.

**Flag:** `pwn.college{MvUNsMeXlVxuvGfhEGB8BZ5Vj8A.QX0IDO0wSM2EzNzEzW}`

**commands used**
```
/challenge/run /challenge/files/file_[bash]
```

## Multiple Globs
In this challenge the goal was to use a short (≤3 characters) globged word with two * globs that matches every filename containing the letter p. From my home directory I ran cd /challenge/files, then executed /challenge/run * p * (which expands to all files containing p) to obtain the flag.

**Flag:** `pwn.college{InyPGa44PyDm1OSJJoKFiRlBK3B.0lM3kjNxwSM2EzNzEzW}`

**commands used**
```
cd /challenge/files
/challenge/run *p*
```

## Mixing Globs
In this challenge the goal was to write a short (≤6 chars) glob that matches challenging, educational, and pwning. From my home directory I ran cd /challenge/files, then executed /challenge/run [cep]* (which expands to those three filenames) and obtained the flag.

**Flag:** `pwn.college{gdNWXfIIkX5qRhA4nWh-cpXHjeZ.QX1IDO0wSM2EzNzEzW}`

**challenge used**
```
cd /challenge/files
/challenge/run [cep]*
```

## Exclusionary Globbing
In this challenge the goal was to use an exclusionary bracket glob so the argument to /challenge/run matches all files that don't start with p, w, or n. From my home directory I ran cd /challenge/files, then executed /challenge/run [^pwn]* (which expands to every filename not beginning with p, w, or n) and obtained the flag.

**Flag:** `pwn.college{QToHv3udK1JvNo42fWVw9xvZqqE.QX2IDO0wSM2EzNzEzW}`

**commands used**
```
cd /challenge/files
/challenge/run [^pwn]*
```

## Tab Completion
In this challenge the goal was to use tab completion to expand a hidden filename. From my home directory I ran cat /challenge/pwn<TAB> (which completed to /challenge/pwncollege) and read the flag.

**Flag:** `pwn.college{AYMYzFOYn6baQCWrdrXydPUdzL6.0FN0EzNxwSM2EzNzEzW}`

**commands used**
```
cat challenge/pwncollege
```

## Multiple Options fot Tab Completiom
In this challenge the goal was to use tab‑completion when there are multiple matches to navigate to the flag file. I ran cd /challenge/files, started completing with pwn<TAB> (then explored the completions until I reached pwncollege-flag), and ran cat pwncollege-flag to read the flag.

**Flag:** `pwn.college{cQYBwZ1IlhSOZQM0ocm_UNIMiVF.0lN0EzNxwSM2EzNzEzW}`

**commands used**
```
cd /challenge/files
cat pwncollege-flag
```

## Tab Completion on Commands
In this challenge the goal was to use tab‑completion for a command that starts with pwncollege. I typed pwncollege and hit <TAB>, which completed to pwncollege-27540, ran it, and got the flag.

**Flag:** `pwn.college{c-vUQL8oa-4tbJT78L9NiokJCwM.0VN0EzNxwSM2EzNzEzW}`

**commands used**
```
pwncollege-27540
``` 
