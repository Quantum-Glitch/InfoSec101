# PicoGym Web Exploitation Writeup
Author : [Akshay K M](https://github.com/akshaymurali01)
Challenge Page: [Get aHEAD](http://mercury.picoctf.net:34561/)
## Walkthrough
The second hint says you need to use something called BurpSuite to look at HTTP requests, intercept and modify them if necessary. So I installed Burp, looked at a quick tutorial for how to use it and set it up.

Now I looked at the requests when I clicked the Red and Blue Buttons. One was a GET request and the other was a POST. The first hint says there is more than one option, so i Googled HTTP get and post. The Wikipedia article refers a type of request called HEAD, which is a modified GET request. So in burp, I intercepted a request, changed the GET request to a HEAD request, and in the raw response in burp, the flag was visible.
## Flag
``picoCTF{r3j3ct_th3_du4l1ty_8f878508}``
## Useful Resources

1. [Download Burp Community Edition](https://portswigger.net/burp/communitydownload)
2. [Official Burp Documentation](https://portswigger.net/burp/documentation/contents)
3. [Quick Tutorial of Burp](https://www.hacker101.com/sessions/burp101.html)
4. [HTTP Methods Wikipedia](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods)


