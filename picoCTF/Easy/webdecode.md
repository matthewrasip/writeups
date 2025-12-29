# WebDecode
#### debug info: [u:953389 e: p: c:427 i:295916]

## Description
Do you know how to use the web inspector?

# Approach
As suggested in the description, we started by looking at the pages source code. In the 'About me' page, we see a `<section>` tag with `notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMDdiOTFjNzl9"` attribute. using base64 decoding on this value returns the flag:
```
picoCTF{web_succ3ssfully_d3c0ded_07b91c79}
```