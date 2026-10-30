# EVEN RSA CAN BE BROKEN???
#### debug info: [u:953389 e: p: c:470 i:296797]

## Description
This service provides you an encrypted flag. Can you decrypt it with just N & e?

# Approach
When connecting to the server we recieve:
```
N:21171186590345384309338052913276600713619902445497413711188110709789649728246890320380215781389037147233545872865464849621369115348531091077527329271742018
e: 65537
cyphertext:18944208620168340893994398219937807577402376090496081845872657967232883467679512362576137939394257982996218243738916608158756462242803093998687188085284843
```
We notice that the `N` - which is usually a prime - is even, hence, has a factor of 2 and another value. Using `p` and `q` being 2 and `N/2`, we can calculate `phi(n)` [(p - 1) * (q - 1)], and therefore the private key. Using the private key we can decrypt the ciphertext and convert decimal to hexadecimal, then to text, returning the flag:
```
picoCTF{tw0_1$_pr!m375129bb1}
```
