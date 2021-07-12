# Microcorruption CTF Writeup : Cusco
Level: Cusco
Author: Akshay K M
## Solution
If we enter a password of length greater than 16 characters, we find that some of the data gets overwritten. Therefore, our objective in this level is to make the stack pointer point to the address of the `<unlock_door>` function. To do that, we find the value of the stack pointer when the control reaches the end of the `<login>` function, which is namely `43fe`. Then, after observing that the function `<unlock_door>` is at address `4446`, and that our input starts getting stored from address `43ee` we realise we need 16 bytes of padding, before adding the address `4446`, while keeping in mind the endianness. The password is as follows. 

## Password
`<32 random hexadecimal digits>4644` (as hexadecimal input)
