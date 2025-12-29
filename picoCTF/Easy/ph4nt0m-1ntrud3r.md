# Ph4nt0m 1ntrud3r
#### debug info: [u:953389 e: p: c:459 i:296162]

## Description
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag. To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!

# Approach
Opening the PCAP file with wireshark, we see 22 packets from the same source to the same destination. Some packets have a `len` of 4, 8, or 12. Inspecting the larger packets first, we notice that the TCP segment data appears to be using base64 encoding (as hinted by sufix `==`). Decoding this initial packet returns `picoCTF`. Using the same method on the following packets of length 12 return the flag:
```
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_959f50d3}
```