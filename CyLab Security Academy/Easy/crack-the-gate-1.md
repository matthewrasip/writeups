# Crack the Gate 1
#### debug info: [u:953389 e: p: c:520 i:296906]

## Description
We’re in the middle of an investigation. One of our persons of interest, ctf player, is believed to be hiding sensitive data inside a restricted web portal. We’ve uncovered the email address he uses to log in: ctf-player@picoctf.org. Unfortunately, we don’t know the password, and the usual guessing techniques haven’t worked. But something feels off... it’s almost like the developer left a secret way in. Can you figure it out?

# Approach
Launching the site we are meant by a standard login screen. Analysing the HTML, we notice two comments:
```
ABGR: Wnpx - grzcbenel olcnff: hfr urnqre "K-Qri-Npprff: lrf"
Remove before pushing to production! 
``` 
This is evidently using a Caesar cipher, hence, decoidng this results in: `NOTE: Jack - temporary bypass: use header "X-Dev-Access: yes"`. We can exploit this vulnerability by using Burp Suite and adding the `X-Dev-Access: yes` header to our packet - by intercepting the packet before it reaches the server.<br><br>
Doing so returns the flag `picoCTF{brut4_f0rc4_49d1d186}`