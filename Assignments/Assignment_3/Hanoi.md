# Microcorruption CTF Writeup : Hanoi
Level: Hanoi
Author: Akshay K M
## Solution
Looking at the `<login>` function, we can see that due to the following lines:
```455a:  f290 9e00 1024 cmp.b	#0x9e, &0x2410  
4560:  0720           jne	#0x4570 <login+0x50>  
4562:  3f40 f144      mov	#0x44f1 "Access granted.", r15  
4566:  b012 de45      call	#0x45de <puts>
456a:  b012 4844      call	#0x4448 <unlock_door>
```
The data stored in the address `0x2410` must be `0x9e`. By testing a random password, we can see that the data starts getting stored from `0x2400`. So we give a hexadecimal input of 34 character length ending with `9e`.

## Password
`<32 random hexadecimal digits>9e` (as hexadecimal input)
