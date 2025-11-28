# Riddle Registry
#### debug info: [u:953389 e: p: c:530 i:297166]

## Description
Hi, intrepid investigator! 📄🔍 You've stumbled upon a peculiar PDF filled with what seems like nothing more than garbled nonsense. But beware! Not everything is as it appears. Amidst the chaos lies a hidden treasure—an elusive flag waiting to be uncovered. Find the PDF file here Hidden Confidential Document and uncover the flag within the metadata.

# Approach
Following the instructions of the description, we view the PDF file's metadata.
```
Author:          cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV9mOTQzMDBjNH0=
Producer:        PyPDF2
Custom Metadata: no
Metadata Stream: no
Tagged:          no
UserProperties:  no
Suspects:        no
Form:            none
JavaScript:      no
Pages:           1
Encrypted:       no
Page size:       612 x 792 pts (letter)
Page rot:        0
File size:       182705 bytes
Optimized:       no
PDF version:     1.7
```
The author appears to have base64 encoding (as suggested by the ending '='). Decoding the author's name returns `picoCTF{puzzl3d_m3tadata_f0und!_f94300c4}` - hence, here is the flag.
