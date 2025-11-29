# hashcrack
#### debug info: [u:953389 e: p: c:475 i:296836]

## Description
A company stored a secret message on a server which got breached due to the admin using weakly hashed passwords. Can you gain access to the secret stored within the server?

# Approach
Upon connecting to the server, we are met with text that follows:
```
We have identified a hash: 482c811da5d5b4bc6d497ffa98491e38
Enter the password for identified hash: 
```
As suggested in the title, we know that we must crack the hashes that are presented in the terminal. The first hash yeilds `password123`. Entering that returns:
```
Flag is yet to be revealed!! Crack this hash: b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3
Enter the password for the identified hash:
```
This hash is identified as `letmein`. Entering that proceeds with:
```
Almost there!! Crack this hash: 916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745
Enter the password for the identified hash: 
```
This SHA256 hash returns `qwerty098`. Entering that returns the flag:
```
Correct! You've cracked the SHA-256 hash with a secret found. 
The flag is: picoCTF{UseStr0nG_h@shEs_&PaSswDs!_4c95d69f}
```