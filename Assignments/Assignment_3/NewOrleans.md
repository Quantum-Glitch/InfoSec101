# Microcorruption CTF Writeup : New Orleans
Level: New Orleans
Author: Akshay K M
## Solution
Looking at the `<main>` function, we see a function called `<check_password>`. Putting a breakpoint there and analysing the function, we see that it compares the data stored at the address stored at register 13 to the data stored at `0x2400`. We check out the memory dump to see the contents stored at `0x2400` and see a suspicious random string of alphanumeric characters. Trying that out as the password gets us in!

## Password
`]#W8@Wt`
