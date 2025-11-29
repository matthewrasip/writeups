# DISKO 1
#### debug info: [u:953389 e: p: c:505 i:296556]

## Description
Can you find the flag in this disk image?

# Approach
We retrieve the disk file named `disko-1.dd.gz`. Noticing that the file is zipped/compressed, we can run `gunzip disko.dd.gz` to retrieve the unzipped disk file. Following the hint that "Strings could help", we realise that we can run `strings disko.dd | grep "pico"` to catch any text that could have the flag. Doing so returns:
```
:/icons/appicon
# $Id: piconv,v 2.8 2016/08/04 03:15:58 dankogai Exp $
piconv -- iconv(1), reinvented in perl
  piconv [-f from_encoding] [-t to_encoding]
  piconv -l
  piconv -r encoding_alias
  piconv -h
B<piconv> is perl version of B<iconv>, a character encoding converter
a technology demonstrator for Perl 5.8.0, but you can use piconv in the
piconv converts the character encoding of either STDIN or files
Therefore, when both -f and -t are omitted, B<piconv> just acts
picoCTF{1t5_ju5t_4_5tr1n9_be6031da}
```
Hence the flag is `picoCTF{1t5_ju5t_4_5tr1n9_be6031da}`.