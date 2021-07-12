# Microcorruption CTF Writeup : Sydney
Level: Sydney
Author: Akshay K M
## Solution
Looking at the `<main>` function, we see a function called `<check_password>`. Putting a breakpoint there and analysing the function, we see that the function compares bits of the entered password to some hexadecimal values, which are `3b45 , 3d6d , 606c , 682c`. We have to enter these values as hexadecimal input. Due to little endianness of storage of data, we have to flip every block of 2 bits, therefore the final password is as follows.

## Password
`453b6d3d6c602c68` (as hexadecimal input)
