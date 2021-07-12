# PicoGym Web Exploitation Writeup
Author : [Akshay K M](https://github.com/akshaymurali01)  
Challenge Page: [where are the robots](https://jupiter.challenges.picoctf.org/problem/60915/)
## Walkthrough
The title itself gives a hint on how to proceed. The first hint also points us towards some part of the website where we can hide some part of the website (?). After some googling I found a Stackoverflow post which referenced something called ``robots.txt``.

I went to ``<challenge_page>/robots.txt`` and  in it was a reference to an html file called ``8028f.html.`` Going to ``<challenge_page>/8028f.html`` gives the flag.
## Flag
``picoCTF{ca1cu1at1ng_Mach1n3s_8028f}``
## Useful Resources

1. [Stackoverflow post](https://stackoverflow.com/questions/13392751/how-do-you-hide-part-website-from-search-engines)
2. [What is robots.txt?](https://developers.google.com/search/docs/advanced/robots/intro)
