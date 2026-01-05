# interencdec
#### debug info: [u:953389 e: p: c:418 i:296006]

## Description
Can you get the real meaning from this file.

# Approach
After downloading the file, we can `cat` it to see its contents:
```
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6ZzVNR3N5TXpjNWZRPT0nCg==
```
Knowing this is base64 encoding (`==` suffix) we can decode it to reveal the following message:
```
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzg5MGsyMzc5fQ=='
```
Again, we see base64 encoding, so removing the `b''` from the string we can decode it to:
```
wpjvJAM{jhlzhy_k3jy9wa3k_890k2379}
```
Inspecting the way that this string is formated/laid out, we notice that it has the same pattern as pico flags - being `picoCTF{...}`. The string starts with four lowercase letters, followed by three uppercase, just like `picoCTF`. Hence, we used a Caesar cipher on the string to reveal the flag:
```
picoCTF{caesar_d3cr9pt3d_890d2379}
```