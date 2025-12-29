# Scan Surprise
#### debug info: [u:953389 e: p: c:444 i:295570]

## Description
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?

# Approach
Using the provided address and password we are able to ssh to the server. Upon entering the password we are greeted with a QR code. Scanning it with your mobile phone will return the flag:
```
picoCTF{p33k_@_b00_19eccd10}
```