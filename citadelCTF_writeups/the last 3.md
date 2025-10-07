# CitadelCTF
Over all as this was my first ctf I was only able to reach challenge 11 I was a bit disappointed with myself but what can we do the onlything i can do ...is improve myself and hope my bet for the future. I will do much better in the next one for sure.
So the last three of my challenges were:
## Rotting in the Deep
Two of the files were given one had a code and other a big numerical line of digits that was the flag converted into integer and each digit was shifted by three and to reverse that we just had to run a simple code.

***Flag:** citadel{br0_r34lly_unr0tt3d_m3_b4ck_t0_l1f3}

**CODE :**
```
from Crypto.Util.number import *
ct = '6895840967002953721051398351211751734500850509315790892845302801984496338433523326225010635779036738800318'
flag = ''
for digit in ct:
    flag += str((int(digit)-3)%10)

print(long_to_bytes(int(flag)))
```

## The Robot's Trail
This one was easy but a bit long , you just had to use inspect on the first site then you'll see  the clue then go on that then there was one more clue then ther was hidden address you'll get for the flag.txt you just had to copy paste the address and you'll get the flag.

## Selected Ambient Work
This one was easy...that's what i thought, even though it was but it was tricky too, first i used morse audio decoder it gave me a whole sentenceand that was wrong but after i changed the software a few times it gave me the same sentence so i thought maybe i have to pay more attention to it then i saw in the spectro graph i found citadel{     } then i came to know the part that was the flag.
